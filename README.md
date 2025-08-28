
# 🔍 Scanner Industrial Multiprotocolo

Ferramenta em **Python** para varredura de rede e identificação de dispositivos industriais, com suporte a múltiplos protocolos, exportação direta para **CSV** e relatório resumido.

⚠️ **Aviso de uso responsável:** utilize **apenas** em redes de teste, ambientes controlados ou com **permissão explícita**. Varreduras não autorizadas podem ser interpretadas como atividade maliciosa e causar impacto em equipamentos sensíveis.

---

## ✨ Funcionalidades
- Detecção de **EtherNet/IP**, **Modbus TCP**, **HTTP/HTTPS** e **SNMP**
- Varredura **TCP e UDP**
- **Banner grabbing** para identificar fabricante/versão
- **Exportação CSV** com data/hora no nome do arquivo
- **Resumo estatístico** ao final da execução
- Execução **multithread** para melhor desempenho

---

## 📦 Instalação

1. **Clone o repositório**
   ```bash
   git clone https://github.com/seuusuario/scanner-industrial.git
   cd scanner-industrial
   ```

2. **Verifique se o Python 3.7+ está instalado**
   ```bash
   python --version
   ```

3. **(Opcional) Crie um ambiente virtual**
   ```bash
   python -m venv venv
   source venv/bin/activate   # Linux/macOS
   venv\Scripts\activate      # Windows
   ```

4. **Instale dependências (se necessário)**  
   O script usa apenas bibliotecas padrão do Python.

---

## ⚙️ Configuração e Uso

Edite no início do script os parâmetros principais:

```python
NETWORK = ipaddress.IPv4Network("192.168.0.0/24", strict=False)  # Rede-alvo
TIMEOUT = 0.5      # Tempo de espera por resposta
NUM_THREADS = 100  # Número de threads
```

Execute no terminal:
```bash
python scanner_industrial.py
```

Ao término:
- Os resultados são exibidos no terminal
- Um arquivo CSV será salvo no formato:
  ```
  scan_resultados_YYYYMMDD_HHMMSS.csv
  ```

---

## 📡 Protocolos Suportados

| Protocolo   | Porta  | Transporte | Descrição |
|-------------|--------|-----------|-----------|
| EtherNet/IP | 44818  | TCP       | Protocolo muito usado em automação industrial (Allen-Bradley, Rockwell) |
| Modbus TCP  | 502    | TCP       | Comunicação simples, padrão de mercado industrial |
| HTTP        | 80     | TCP       | Interface web de dispositivos |
| HTTPS       | 443    | TCP       | Interface web segura |
| SNMP        | 161    | UDP       | Gerenciamento e monitoramento de rede |

---

## 🛡 Boas Práticas
- Sempre **obtenha autorização** antes de qualquer varredura
- Execute em janelas de manutenção ou ambientes isolados
- Documente os resultados para auditoria e inventário
- Avalie integrar modos **passivos** para diagnóstico de baixo impacto

---

