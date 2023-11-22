<h2 style="text-align: center;">Relatório de partida</h3>

<h3 style="text-align: center;">{{game.get("match").get("event").get("homeTeam").get("name")}} {{game.get("match").get("event").get("homeScore").get("display")}} x {{game.get("match").get("event").get("awayScore").get("display")}} {{game.get("match").get("event").get("awayTeam").get("name")}}</h3>

<h3 style="text-align: center;"><img src="https://api.sofascore.com/api/v1/player/{{player.get("player").get("id")}}/image">#{{player.get("shirtNumber")}} - {{player.get("player").get("name")}} ({{player.get("player").get("position")}}) - {{player.get("statistics").get("rating", 0)}}</h3>

<div style="text-align: left; display: grid; grid-template-columns: 1fr 1fr;">
  <div>
    <h4 style="text-align: center;">MAPA DE CALOR</h3>
    <img src=../players/heatmaps/{{game.get("match").get("event").get("id")}}_{{player.get("player").get("id")}}.png>
</div>
  <div>
    <h4 style="text-align: center;">MAPA DE CHUTES</h3>
    <img src=../players/shotmaps/{{game.get("match").get("event").get("id")}}_{{player.get("player").get("id")}}.png>
  </div>
</div>

<h4 style="text-align: center;">ESTATÍSTICAS</h3>
<div style="text-align: center; display: grid; grid-template-columns: 1fr;">
  <div>
    <table>
        {% for name, value in statistics.items() %}<tr>
            <td>{{ name }}
            </td>
            <td>{{value}}
            </td>
        </tr>{% endfor %}
        </table>
</div>
