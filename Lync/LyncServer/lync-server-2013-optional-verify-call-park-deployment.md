---
title: 'Lync Server 2013 : (Facultatif) Vérification du déploiement du parcage d’appel'
TOCTitle: (Facultatif) Vérification du déploiement du parcage d’appel
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413076(v=OCS.15)
ms:contentKeyID: 49299438
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Facultatif) Vérification du déploiement du parcage d’appel dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-11_

Une fois que vous avez installé et configuré le parcage d’appel, vérifiez sa configuration pour vous assurer que le parcage et la récupération d’appel fonctionnent comme prévu. Vérifiez au minimum les éléments suivants :

  - Appelez un utilisateur qui a activé le parcage d’appel et demandez-lui de parquer l’appel.
    
    > [!NOTE]  
    > Si vous avez activé le parcage d’appel dans une stratégie de voix juste avant de procéder à ce test, l’utilisateur qui parque l’appel doit se déconnecter de Lync Server puis se connecter à nouveau pour pouvoir voir l’option parcage d’appel dans la liste de transfert d’appel.

  - Composez le numéro orbite pour récupérer l’appel.

  - Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est correctement acheminé vers la destination secondaire spécifiée pour **OnTimeoutURI** .

