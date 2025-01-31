import { useState, useEffect } from "react";
import Head from "next/head";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";

export default function CareerManager() {
  const [teams, setTeams] = useState([]);
  const [players, setPlayers] = useState([]);
  const [coachStats, setCoachStats] = useState({});
  const [leagues, setLeagues] = useState([]);
  const [trophies, setTrophies] = useState([]);
  const [playerOveralls, setPlayerOveralls] = useState([]);

  useEffect(() => {
    const storedTeams = JSON.parse(localStorage.getItem("teams")) || [];
    const storedPlayers = JSON.parse(localStorage.getItem("players")) || [];
    const storedCoachStats = JSON.parse(localStorage.getItem("coachStats")) || {};
    const storedLeagues = JSON.parse(localStorage.getItem("leagues")) || [];
    const storedTrophies = JSON.parse(localStorage.getItem("trophies")) || [];
    const storedPlayerOveralls = JSON.parse(localStorage.getItem("playerOveralls")) || [];

    setTeams(storedTeams);
    setPlayers(storedPlayers);
    setCoachStats(storedCoachStats);
    setLeagues(storedLeagues);
    setTrophies(storedTrophies);
    setPlayerOveralls(storedPlayerOveralls);
  }, []);

  useEffect(() => {
    localStorage.setItem("teams", JSON.stringify(teams));
    localStorage.setItem("players", JSON.stringify(players));
    localStorage.setItem("coachStats", JSON.stringify(coachStats));
    localStorage.setItem("leagues", JSON.stringify(leagues));
    localStorage.setItem("trophies", JSON.stringify(trophies));
    localStorage.setItem("playerOveralls", JSON.stringify(playerOveralls));
  }, [teams, players, coachStats, leagues, trophies, playerOveralls]);

  const addTeam = () => {
    const newTeam = prompt("Nome do novo time:");
    if (newTeam) setTeams([...teams, newTeam]);
  };

  const addPlayer = () => {
    const newPlayer = prompt("Nome do novo jogador:");
    if (newPlayer) setPlayers([...players, newPlayer]);
  };

  return (
    <>
      <Head>
        <title>Gerenciador de Modo Carreira</title>
        <meta name="description" content="Gerencie seu modo carreira no EA FC 25" />
      </Head>
      <div className="p-6 grid grid-cols-1 md:grid-cols-2 gap-6">
        <Card>
          <CardContent>
            <h2 className="text-xl font-bold">Gestão do Elenco</h2>
            <Button className="mt-4" onClick={addPlayer}>Adicionar Jogador</Button>
          </CardContent>
        </Card>

        <Card>
          <CardContent>
            <h2 className="text-xl font-bold">Times</h2>
            <Button className="mt-4" onClick={addTeam}>Adicionar Time</Button>
          </CardContent>
        </Card>
      </div>
    </>
  );
}
