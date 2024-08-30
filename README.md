# Função para coletar as preferências do usuário
def coletar_preferencias():
    print("Vamos descobrir qual jogo combina mais com você!")
    genero = input("Qual é o seu gênero favorito? (RPG, Aventura, Ação, Esporte, Corrida, Luta, Estratégia, Puzzle): ").strip().lower()
    plataforma = input("Qual plataforma você prefere? (PC, Console, Mobile): ").strip().lower()
    estilo = input("Você prefere um jogo mais calmo, competitivo ou cooperativo? (Calmo, Competitivo, Cooperativo): ").strip().lower()
    anime = input("Você gosta de jogos baseados em animes? (Sim, Não): ").strip().lower()
    graficos = input("Você prefere gráficos mais realistas ou estilizados? (Realistas, Estilizados): ").strip().lower()
    return genero, plataforma, estilo, anime, graficos

# Base de dados de jogos
jogos = [
    {"nome": "The Witcher 3", "genero": "rpg", "plataforma": "pc", "estilo": "calmo", "anime": "não", "graficos": "realistas"},
    {"nome": "FIFA 23", "genero": "esporte", "plataforma": "console", "estilo": "competitivo", "anime": "não", "graficos": "realistas"},
    {"nome": "Genshin Impact", "genero": "rpg", "plataforma": "mobile", "estilo": "calmo", "anime": "sim", "graficos": "estilizados"},
    {"nome": "Dragon Ball FighterZ", "genero": "luta", "plataforma": "console", "estilo": "competitivo", "anime": "sim", "graficos": "estilizados"},
    {"nome": "League of Legends", "genero": "estratégia", "plataforma": "pc", "estilo": "competitivo", "anime": "não", "graficos": "estilizados"},
    {"nome": "Mario Kart 8", "genero": "corrida", "plataforma": "console", "estilo": "competitivo", "anime": "não", "graficos": "estilizados"},
    {"nome": "Persona 5", "genero": "rpg", "plataforma": "console", "estilo": "calmo", "anime": "sim", "graficos": "estilizados"},
    {"nome": "Fortnite", "genero": "ação", "plataforma": "pc", "estilo": "competitivo", "anime": "não", "graficos": "estilizados"},
    {"nome": "Minecraft", "genero": "aventura", "plataforma": "pc", "estilo": "cooperativo", "anime": "não", "graficos": "estilizados"},
    {"nome": "Naruto Shippuden: Ultimate Ninja Storm 4", "genero": "luta", "plataforma": "console", "estilo": "competitivo", "anime": "sim", "graficos": "estilizados"},
]

# Função que recomenda o jogo com base nas preferências
def recomendar_jogo(preferencias):
    genero, plataforma, estilo, anime, graficos = preferencias
    for jogo in jogos:
        if (jogo["genero"] == genero and 
            jogo["plataforma"] == plataforma and 
            jogo["estilo"] == estilo and 
            jogo["anime"] == anime and 
            jogo["graficos"] == graficos):
            return jogo["nome"]
    return "Desculpe, não encontramos um jogo que combine com suas preferências."

# Coletar as preferências do usuário
preferencias_usuario = coletar_preferencias()

# Recomendar o jogo mais adequado
jogo_recomendado = recomendar_jogo(preferencias_usuario)
print(f"O jogo que mais combina com você é: {jogo_recomendado}")

