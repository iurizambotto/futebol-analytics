<h2 style="text-align: center;">Relatório de partida</h3>

<h3 style="text-align: center;">{{game.get("match").get("event").get("homeTeam").get("name")}} {{game.get("match").get("event").get("homeScore").get("display")}} x {{game.get("match").get("event").get("awayScore").get("display")}} {{game.get("match").get("event").get("awayTeam").get("name")}}</h3>

<h3 style="text-align: center;">ESCALAÇÕES</h3>

<div style="text-align: left; display: grid; grid-template-columns: 1fr 1fr;">
  <div>
    <h4>{{game.get("match").get("event").get("homeTeam").get("name")}}</h4>
    <h5>Restrospecto: {{game.get("match").get("event").get("home_retrospecto")}}</h5>
    <table>
        <h5>TITULARES ({{game.get("match").get("lineups").get("home").get("formation")}})</h5>
        <th>
        #
        </th>
        <th>
        Nome
        </th>
        <th>
        Posição
        </th>
        <th>
        Score
        </th>
        {% for player in game.get("match").get("lineups").get("home").get("players") %}{% if not player.get("substitute") %}<tr>
            <td>#{{player.get("shirtNumber")}}
            </td>
            <td><a href="../players/{{game.get("match").get("event").get("id")}}_{{player.get("player").get("id")}}.md">{{player.get("player").get("name")}}</a>
            </td>
            <td>{{player.get("player").get("position")}}
            </td>
            <td>{{player.get("statistics").get("rating", 0)}}
            </td>
        </tr>{%endif%}{% endfor %}
        </table>
        <table>
        <h5> RESERVAS</h5>
        <th>
        #
        </th>
        <th>
        Nome
        </th>
        <th>
        Posição
        </th>
        <th>
        Score
        </th>
        {% for player in game.get("match").get("lineups").get("home").get("players") %}{% if player.get("substitute") %}<tr>
            <td>#{{player.get("shirtNumber")}}
            </td>
            <td><a href="../players/{{game.get("match").get("event").get("id")}}_{{player.get("player").get("id")}}.md">{{player.get("player").get("name")}}</a>
            </td>
            <td>{{player.get("player").get("position")}}
            </td>
            <td>{{player.get("statistics").get("rating", 0)}}
            </td>
        </tr>{%endif%}{% endfor %}
     </table>
</div>
  <div>
    <h4>{{game.get("match").get("event").get("awayTeam").get("name")}}</h4>
    <h5>Restrospecto: {{game.get("match").get("event").get("away_retrospecto")}}</h5>
    <table>
        <h5>TITULARES ({{game.get("match").get("lineups").get("away").get("formation")}})</h5>
        <th>
        #
        </th>
        <th>
        Nome
        </th>
        <th>
        Posição
        </th>
        <th>
        Score
        </th>
        {% for player in game.get("match").get("lineups").get("away").get("players") %}{% if not player.get("substitute") %}<tr>
            <td>#{{player.get("shirtNumber")}}
            </td>
            <td><a href="../players/{{game.get("match").get("event").get("id")}}_{{player.get("player").get("id")}}.md">{{player.get("player").get("name")}}</a>
            </td>
            <td>{{player.get("player").get("position")}}
            </td>
            <td>{{player.get("statistics").get("rating", 0)}}
            </td>
        </tr>{%endif%}{% endfor %}
        </table>
        <table>
        <h5> RESERVAS</h5>
        <th>
        #
        </th>
        <th>
        Nome
        </th>
        <th>
        Posição
        </th>
        <th>
        Score
        </th>
        {% for player in game.get("match").get("lineups").get("away").get("players") %}{% if player.get("substitute") %}<tr>
            <td>#{{player.get("shirtNumber")}}
            </td>
            <td><a href="../players/{{game.get("match").get("event").get("id")}}_{{player.get("player").get("id")}}.md">{{player.get("player").get("name")}}</a>
            </td>
            <td>{{player.get("player").get("position")}}
            </td>
            <td>{{player.get("statistics").get("rating", 0)}}
            </td>
        </tr>{%endif%}{% endfor %}
     </table>
  </div>
</div>

<h3 style="text-align: center;">POSIÇÕES MÉDIAS</h3>
<img src=avg_positions/{{game.get("match").get("event").get("id")}}.png>
