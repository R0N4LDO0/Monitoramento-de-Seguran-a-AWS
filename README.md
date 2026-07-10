# 🛡️ Monitoramento de Segurança AWS  

Este projeto tem como objetivo criar um sistema automatizado de monitoramento de segurança na AWS, capaz de identificar atividades suspeitas e enviar alertas em tempo real. A solução utiliza CloudWatch, SNS e o SDK Boto3 para coletar logs, analisar eventos e notificar o time de segurança.

# ⚙️ Tecnologias Utilizadas 
🐍 Python 3.10+

☁️ AWS CloudWatch & SNS

🔐 IAM Roles

🧱 Terraform (opcional) para provisionamento da infraestrutura

 # 🧩 Estrutura do Projeto 

 <img width="643" height="293" alt="image" src="https://github.com/user-attachments/assets/98310ffd-59cd-4b66-979e-c30b3194d192" />


# 🧠 Exemplo de Código (monitor.py)  



Importação BOTO3 JSON de importação de alert_manager e função send_alert

```python
import boto3
from alert_manager import send_alert

def monitorar_logs():
    client = boto3.client('logs')
    response = client.filter_log_events(
        logGroupName='/aws/lambda/meu-servico',
        filterPattern='ERRO'
    )

    for event in response.get('events', []):
        mensagem = event['message']
        if "unauthorized" in mensagem.lower():
            send_alert(f"Acesso não autorizado detectado: {mensagem}")

if __name__ == "__main__":
    monitorar_logs()
```






# 🚨 Funcionalidades 
🔍 Monitoramento contínuo de logs do CloudWatch

⚠️ Detecção de padrões de erro e acesso não autorizado

📩 Envio automático de alertas via SNS

🧩 Configuração simples e escalável

# 📈 Melhorias Futuras
💡 Integração com AWS GuardDuty

💡 Dashboard de alertas com Grafana

💡 Machine Learning para detecção de anomalias 

# 👨‍💻 Autor
**Ronaldo de Sousa Gonçalves**  
Especialista em Cibersegurança | DevSecOps
📍 Brasília - DF
🔗 LinkedIn (https://www.linkedin.com/in/ronaldo-sousa-7904b61a2/)

