#include <stdio.h>
#include <stdlib.h>

// Definição da estrutura Canal
typedef struct {
    char tipo[20]; // Tipo de canal: WhatsApp, Telegram, Facebook, Instagram
    char identificador[50]; // Número de telefone ou nome de usuário
} Canal;

// Definição da estrutura Mensagem
typedef struct {
    char tipo[10]; // Tipo de mensagem: Texto, Vídeo, Foto, Arquivo
    char conteudo[200]; // Conteúdo da mensagem
    char data_envio[20]; // Data de envio
} Mensagem;

// Função para enviar mensagem para um canal específico
void enviar_mensagem(Canal canal, Mensagem mensagem) {
    printf("Enviando mensagem para %s %s: %s - Enviada em: %s\n", canal.tipo, canal.identificador, mensagem.conteudo, mensagem.data_envio);
}

int main() {
    // Exemplo de uso
    Canal whatsapp_contato = {"WhatsApp", "+55123456789"};
    Mensagem mensagem_texto = {"Texto", "Olá, como vai?", "2023-12-04 15:30"};

    enviar_mensagem(whatsapp_contato, mensagem_texto);

    Canal facebook_contato = {"Facebook", "usuario123"};
    Mensagem mensagem_video = {"Vídeo", "video.mp4", "30s", "2023-12-04 16:45"};

    enviar_mensagem(facebook_contato, mensagem_video);

    return 0;
}
