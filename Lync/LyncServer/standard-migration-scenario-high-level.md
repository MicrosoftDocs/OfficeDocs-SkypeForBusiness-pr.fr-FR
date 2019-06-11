---
title: Scénario de migration standard - Haut niveau
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69349b90c6845d8a3f3d5ed13544da4fe4832eb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>Scénario de migration standard - Haut niveau

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-30_

Utilisez les éléments suivants comme point de départ lors de la migration de Lync Server 2010, d’une conversation de groupe ou d’une conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de chat permanent. Le chemin de migration standard de Lync Server 2013 est le suivant:

  - Votre organisation a déjà déployé Lync Server 2010, les discussions de groupe ou les discussions de groupe Office Communications Server 2007 R2 et vous voulez déployer Lync Server 2013, serveur de conversation permanent.

  - Déploiement de Lync Server 2013, puis déploiement du ou des pools de serveurs de chat permanents.

  - Préparez et planifiez la migration de vos salles de conversation permanente et déterminez un moment approprié pour arrêter le système à des fins de migration.

  - Exécutez les cmdlets Windows PowerShell pour la migration (**Export-CsPersistentChatData** et **Import-CsPersistentChatData**) pour déplacer le contenu vers le serveur de conversation persistante.

  - Vérifiez que la migration a réussi.

  - Désaffectez votre déploiement hérité.

  - Configurez le serveur de chat permanent de sorte que les clients hérités puissent se connecter à Lync Server 2013, serveur de chat permanent. Cela est nécessaire, car cela prend du temps pour le déploiement de nouveaux clients, et vous voulez permettre aux utilisateurs existants d’avoir accès à leurs salles de conversation le plus rapidement possible.

  - Déployez de nouveaux clients tout en continuant de garantir que les travailleurs disposant d’une discussion de groupe héritée (clients) pourront accéder à leurs salles de conversation.

</div>

<span> </span>

</div>

</div>

</div>

