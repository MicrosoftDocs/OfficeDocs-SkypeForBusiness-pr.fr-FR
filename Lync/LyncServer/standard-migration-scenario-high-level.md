---
title: Scénario de migration standard-haut niveau
description: Scénario de migration standard-haut niveau.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a931b76e528b7e6468f6b7e7b9a718724d27501f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573160"
---
# <a name="standard-migration-scenario---high-level"></a>Scénario de migration standard-haut niveau

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

Utilisez les éléments suivants comme point de départ lors de la migration de Lync Server 2010, Group chat ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de conversation permanente. Le chemin d’accès de migration standard de Lync Server 2013 se présente comme suit :

  - Votre organisation a précédemment déployé Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat, et vous souhaitez déployer Lync Server 2013, serveur de conversation permanente.

  - Déployez Lync Server 2013, puis déployez le ou les pools de serveurs de conversation permanente.

  - Préparez et planifiez la migration de vos salles de conversation permanente et déterminez une heure appropriée pour arrêter le système pour la migration.

  - Exécutez les applets de commande Windows PowerShell pour la migration (**Export-applet cspersistentchatdata** et **Import-applet cspersistentchatdata**) pour déplacer le contenu vers le serveur de conversation permanente.

  - Vérifiez que la migration a réussi.

  - Désactivez votre déploiement hérité.

  - Configurez le serveur de conversation permanente de sorte que les clients hérités puissent se connecter à Lync Server 2013, serveur de conversation permanente. Cette action est nécessaire, car le déploiement de nouveaux clients prend du temps, et les utilisateurs existants avec des clients hérités doivent avoir accès à leurs salles de conversation dès que possible.

  - Déployez de nouveaux clients, tout en continuant à s’assurer que les travailleurs disposant d’une conversation de groupe héritée (clients) peuvent accéder à leurs salles de conversation.

</div>

<span> </span>

</div>

</div>

</div>

