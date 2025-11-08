# Transcrição e Diarização de diálogos com WhisperX

Projeto para transcrição e diarização de áudios usando WhisperX.

Conteúdo principal:
- `whisperx.ipynb` - notebook principal com fluxo de transcrição, alinhamento e diarização.
- `transcripts/` - saída de transcrições em texto.
- `diarization/` - saída de diarizações em texto.

Como usar

1. Crie uma pasta `audios/` e coloque os arquivos `.m4a` em `audios/raw_m4a/`. Caso o áudio esteja em outro formato, será necessário adaptar no notebook.

2. Abra e execute o notebook `whisperx.ipynb` no Jupyter/VS Code.

Notas importantes

- O notebook usa GPU (device `cuda`) por padrão. Se estiver em CPU, altere `device = "cpu"` e ajuste `compute_type`.
- A transcrição usa o modelo `large-v2` por padrão. Mude para modelos menores se tiver memória limitada.
 

Backlog:

- Parametrizar diretórios, device, batch_size e modelo via argumentos ou arquivo `config.yaml`.
- Reutilizar o modelo em vez de recarregá-lo por arquivo quando possível (economiza tempo/VRAM).
- Tratar erros e adicionar logging (módulo `logging`) para acompanhar execução longa.
- Validar formatos de arquivo e criar um passo de conversão para WAV quando necessário.
- Adicionar testes unitários básicos e um script CLI pequeno (`transcribe.py`) para automação.
- Implementação de `requirements.txt`
