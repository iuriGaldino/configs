# MangoHud Configuration

Este arquivo contém a configuração personalizada do **MangoHud** para monitoramento de desempenho em jogos no Linux.

## 📌 Caminho do Arquivo
O arquivo de configuração deve ser salvo em:

```
~/.config/MangoHud/MangoHud.conf
```

## ⚙️ Configuração
```ini
##########################
# MangoHud Configuration #
##########################

# 🎯 FPS e Sincronização
#fps_limit=60          # Limita o FPS para evitar consumo excessivo
vsync=0               # Desativa VSync (0 = off, 1 = on)
frametime=1           # Mostra tempo de renderização de quadros

# 🎯 Estatísticas da GPU
gpu_stats=1           # Ativa monitoramento da GPU
gpu_temp=1            # Exibe temperatura da GPU
gpu_power=1           # Mostra consumo energético da GPU
gpu_clock=1           # Exibe frequência da GPU
vram=1                # Mostra uso da VRAM (memória da GPU)

# 🎯 Estatísticas da CPU
cpu_stats=1           # Ativa monitoramento da CPU
cpu_temp=1            # Exibe temperatura da CPU
cpu_mhz=1             # Exibe frequência da CPU
#core_load=1           # Mostra uso de cada núcleo da CPU

# 🎯 Memória
ram=1                 # Exibe uso da RAM total do sistema

# 🎯 Layout e Aparência
position=top-left     # Define posição na tela (top-left, top-right, bottom-left, bottom-right)
fontsize=14           # Ajusta tamanho da fonte
background_alpha=0.5  # Define transparência do fundo (0.0 a 1.0)
#horizontal=1          # Mostra informações em linha horizontal

# 🎯 Atalhos
toggle_hud=F12        # Tecla para ativar/desativar o MangoHud
toggle_logging=F2     # Ativa/desativa logging de FPS (salvo em ~/.local/share/MangoHud)
```

## 🚀 Como Aplicar as Configurações
1. Criar o diretório de configuração caso não exista:
   ```bash
   mkdir -p ~/.config/MangoHud
   ```
2. Criar ou editar o arquivo:
   ```bash
   nano ~/.config/MangoHud/MangoHud.conf
   ```
3. Copiar e colar a configuração acima e salvar (`Ctrl + X`, `Y`, `Enter`).
4. Para ativar em jogos da Steam:
   - Vá até **Propriedades** do jogo > **Opções de Inicialização** e adicione:
     ```bash
     MANGOHUD=1 %command%
     ```

Agora, ao iniciar um jogo, o **MangoHud** será exibido com essas configurações! 🎮🚀

