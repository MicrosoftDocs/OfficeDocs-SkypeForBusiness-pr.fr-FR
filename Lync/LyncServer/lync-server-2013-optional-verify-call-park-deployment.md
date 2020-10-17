---
title: 'Lync Server 2013 : (facultatif) vérification du déploiement du parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9a22d48e823526f3b4e4b7e6b321ed640328ecd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530811"
---
# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>Module Vérifier le déploiement du parcage d’appel dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-11_

Après avoir installé et configuré le parcage d’appel, vous devez vérifier la configuration pour vous assurer que les appels de parking et de récupération fonctionnent comme prévu. Vérifiez au minimum les éléments suivants :

  - Appelez un utilisateur qui a activé le parcage d’appel et demandez-lui de parkiser l’appel.
    
    <div>
    

    > [!NOTE]  
    > Si vous avez activé le parcage d’appel dans la stratégie de voix juste avant d’effectuer ce test, l’utilisateur qui est responsable de l’appel doit se déconnecter de Lync Server, puis se reconnecter pour pouvoir voir l’option parcage d’appel dans la liste de transfert d’appel.

    
    </div>

  - Composez le numéro orbite pour récupérer l’appel.

  - Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est correctement acheminé vers la destination secondaire qui est spécifiée pour **OnTimeoutURI**.

</div>

<span> </span>

</div>

</div>

</div>

