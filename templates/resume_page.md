<h2 style="text-align: center;">Relatório do time</h3>

<h3 style="text-align: center;"> TIME</h3>

<div style="text-align: center; display: grid; grid-template-columns: 1fr;">
  <div>
    <table>
        <h5>ÚLTIMOS JOGOS</h5>
        <th>
        Casa
        </th>
        <th>
        Fora
        </th>
        <th>
        Placar
        </th>
        <th>
        Data
        </th>
        <th>
        Estádio
        </th>
        {% for game in new_events %}<tr>
            <td><a href="../games/{{game.get("match").get("event").get("id")}}.md">{{game.get("match").get("event").get("homeTeam").get("name")}}</a>
            </td>
            <td>{{game.get("match").get("event").get("awayTeam").get("name")}}
            </td>
            <td>{{game.get("match").get("event").get("homeScore").get("display")}} x {{game.get("match").get("event").get("awayScore").get("display")}}
            </td>
            <td>{{game.get("match").get("event").get("startTimestamp") | format_date }}
            </td>
            </td>
            <td>{{game.get("match").get("event").get("venue").get("stadium").get("name")}}
            </td>
        </tr>{% endfor %}
        </table>
</div>
