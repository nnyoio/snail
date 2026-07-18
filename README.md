간단한 웹 기반 달팽이 경주 베팅 게임입니다.
사용자는 원하는 달팽이를 선택하여 포인트를 베팅하고, 
랜덤하게 진행되는 레이스 결과에 따라 포인트를 획득하거나 잃게 됩니다.

현재는 메인 서버가 연결되어 있지 않습니다.
server.js의

nst NET_CFG = {
  url: ""
};

이곳에 서버 주소를 입력하면 연동할 수 있도록 설계되었습니다.
서버가 연동되지 않은 상태에서는 LocalStorage를 사용하며 시작 포인트는 1000P입니다.

+ 이 게임은 학교에서 도박 예방 교육을 위해 제작한 것으로, 확률이 조작되어 있는 상태가 기본형입니다.
한국어는 확률이 조작되어있는 버전과 없는 버전 2개 둘 다 배포합니다.

This is a simple web-based snail racing betting game.
Players choose one of four snails, place a bet with their points, 
and either win or lose points depending on the randomly determined race result.

The project is designed to work with an external server, but no server is connected by default.

In `server.js`, configure the server URL:

const NET_CFG = {
  url: ""
};

If no server is configured, the game automatically uses LocalStorage to save data locally, 
and each new player starts with 1,000 points.

+ This game was created as part of a school gambling prevention education project.
The default version intentionally uses biased probabilities to demonstrate how manipulated odds can affect gambling outcomes.
The Korean release includes both a biased version and a fair version.

The English release includes only the biased version. 
If you would like to play with completely fair odds, open `probability.js`, 
delete all of its contents, and replace them with the following code:

function pickWinner(bet, profit, natural) {
  return Math.floor(Math.random() * 4);
}

// Fair random winner selection: each of the four snails has a 25% chance of winning.

This changes the game to a completely fair random system in which every snail has an equal 25% chance of winning.
