# add secret

## Add the following lines to the `values.yaml` file in your Helm chart:

```yml
username: root
password: password
```

## Create a new file called `secret.yaml` and add it to the `template` folder. Add the following content to the file

```yml
apiVersion: v1
kind: Secret
metadata:
  name: {{ .Release.Name }}-auth
data:
  password: {{ .Values.password | b64enc }}
  username: {{ .Values.username | b64enc }}
```

## Edit the env section of your Kubernetes deployment to include the new variables defined in the `secret.yaml` file:


```yml
...
      containers:
        - name: {{ .Chart.Name }}
          securityContext:
            {{- toYaml .Values.securityContext | nindent 12 }}
          image: "{{ .Values.image.repository }}:{{ .Values.image.tag | default .Chart.AppVersion }}"
          imagePullPolicy: {{ .Values.image.pullPolicy }}
          env:          
            - name: "USERNAME"
              valueFrom:
                secretKeyRef:
                  key:  username
                  name: {{ .Release.Name }}-auth
            - name: "PASSWORD"
              valueFrom:
                secretKeyRef:
                  key:  password
                  name: {{ .Release.Name }}-auth
...
```

## Test

```
helm template app1 mychart
```
