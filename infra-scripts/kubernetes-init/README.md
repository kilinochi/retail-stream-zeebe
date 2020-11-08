Вот так можно прокинуть на локальную машину дашбоард (не забываем на удаленной тачке выполнить kubectl proxy)

`ssh -L 8001:127.0.0.1:8001 vagrant@192.168.50.101
`
- Токен можно сгенерить командой 

`kubectl get secret -n kubernetes-dashboard $(kubectl get serviceaccount kubernetes-dashboard -n kubernetes-dashboard -o jsonpath="{.secrets[0].name}") -o jsonpath="{.data.token}" | base64 --decode
`
  
  Либо взять из join_command.txt на мастер-ноде при старте кластера