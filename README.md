<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Robô Concordando</title>
  <style>
    body {
      background: #f0f8ff;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .robo {
      width: 60vw;
      height: 70vh;
      background: #064d00; /* verde escuro */
      border-radius: 200px; /* quase oval */
      position: relative;
      box-shadow: 0 8px 25px rgba(0,0,0,0.3);
      animation: flutuar 2s ease-in-out infinite, concordar 2.5s ease-in-out infinite;
    }

    @keyframes flutuar {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-4px); }
    }

    /* movimento de concordar rápido (sim) */
    @keyframes concordar {
      0%, 5%   { transform: translateY(0); }
      10%      { transform: translateY(-15px); } /* sobe */
      15%      { transform: translateY(15px); }  /* desce */
      20%      { transform: translateY(-15px); } /* sobe */
      25%      { transform: translateY(0); }     /* volta */
      50%      { transform: translateY(0); }     /* pausa */
      55%      { transform: translateY(-15px); }
      60%      { transform: translateY(15px); }
      65%      { transform: translateY(-15px); }
      70%      { transform: translateY(0); }
      100%     { transform: translateY(0); }
    }

    /* olhos */
    .olho {
      width: 22vh;
      height: 22vh;
      background: #7CFC00; /* verde claro */
      border-radius: 50%;
      position: absolute;
      top: 23%;
      animation: piscar 3s infinite, fecharOlhos 2.5s ease-in-out infinite;
    }
    .olho.esq { left: 17%; }
    .olho.dir { right: 17%; }

    @keyframes piscar {
      0%, 90%, 100% { transform: scaleY(1); }
      95% { transform: scaleY(0.1); }
    }

    /* olhos fecham levemente no "sim" */
    @keyframes fecharOlhos {
      0%, 5%   { transform: scaleY(1); }
      10%, 20% { transform: scaleY(0.6); } /* fecha um pouco */
      25%      { transform: scaleY(1); }
      55%, 65% { transform: scaleY(0.6); } /* fecha de novo */
      70%      { transform: scaleY(1); }
      100%     { transform: scaleY(1); }
    }

    /* sorriso */
    .boca {
      width: 180px;
      height: 90px;
      background: #7CFC00; /* verde claro */
      border-radius: 0 0 120px 120px;
      position: absolute;
      bottom: 18%;
      left: 50%;
      transform: translateX(-50%);
    }

  </style>
</head>
<body>
  <div class="robo">
    <div class="olho esq"></div>
    <div class="olho dir"></div>
    <div class="boca"></div>
  </div>
</body>
</html>

