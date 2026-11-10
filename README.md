# Tutor ENEM — Configuração das chaves

No Google Colab, abra **Secrets** (ícone de chave na lateral), adicione os valores abaixo e ative o **acesso do notebook** para ambos:

| Nome do Secret | Valor | Onde obter |
| --- | --- | --- |
| `tutorENEM` | Chave da API Gemini | [Google AI Studio](https://aistudio.google.com/) |
| `NGROK_AUTHTOKEN` | Authtoken do ngrok | [Painel do ngrok](https://dashboard.ngrok.com/get-started/your-authtoken) |

Os nomes devem ser exatamente os indicados na tabela. O notebook acessa os valores assim:

```python
import os
from google.colab import userdata
from pyngrok import conf

os.environ["GOOGLE_API_KEY"] = userdata.get("tutorENEM")
conf.get_default().auth_token = userdata.get("NGROK_AUTHTOKEN")
```

Não escreva as chaves diretamente no código nem compartilhe seus valores.
