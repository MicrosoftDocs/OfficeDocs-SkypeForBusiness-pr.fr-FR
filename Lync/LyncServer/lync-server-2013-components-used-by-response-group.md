---
title: 'Lync Server 2013 : composants utilisés par Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b59f96175925c427f77880012f804daf20bf751
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517771"
---
# <a name="components-used-by-response-group-in-lync-server-2013"></a>Composants utilisés par Response Group dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-11_

L’application Response Group est automatiquement activée lorsque vous déployez voix entreprise. Cette section décrit les composants qui prennent en charge l’application Response Group.

<div>

## <a name="response-group-components"></a>Composants de l’application Response Group

Les composants Microsoft Lync Server 2013 suivants prennent en charge l’application Response Group :

  - **Service**     d’application Application service fournit une plateforme permettant de déployer, d’héberger et de gérer des applications de communications unifiées, telles que Response Group. Le service d’application est automatiquement installé sur chaque serveur frontal dans un pool frontal et sur chaque serveur Standard Edition.

  - **Application**     Response Group L’application Response Group est l’une des applications de communications unifiées hébergées par le service d’application. Elle est incluse automatiquement lorsque vous déployez Response Group. L’application Response Group achemine et met en file d’attente les appels entrants vers des groupes d’agents.

  - **Module linguistique**     Un module linguistique est nécessaire pour prendre en charge la reconnaissance vocale et la synthèse vocale. Ces technologies vocales servent lors de la configuration de messages (message de bienvenue et autres messages, ou les questions et réponses d’une réponse vocale interactive, par exemple). Par défaut, les modules linguistiques 26 pris en charge sont installés lorsque vous déployez Lync Server 2013.

  - **Fichiers audio**     Les fichiers audio sont utilisés pour les messages et la musique en attente.

  - **Magasin**     de fichiers Response Group utilise le magasin de fichiers pour stocker les fichiers audio. Plusieurs pools de groupes Response Group peuvent utiliser la même instance du magasin de fichiers.

  - Outil de configuration **Response Group**     L’outil de configuration Response Group est un outil basé sur le Web qui permet de créer et de configurer des groupes Response Group. L’outil de configuration Response Group est inclus lors de l’installation des services Web.

  - **Panneau de configuration**     Microsoft Lync Server 2013 Vous pouvez utiliser le panneau de configuration Lync Server pour installer et configurer des groupes d’agents et des files d’attente pour les groupes Response Group.

  - **Lync Server Management Shell**     Tous les paramètres Response Group peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.

  - **Microsoft Lync 2013**     Les agents formels (les agents qui sont requis pour se connecter au groupe avant de pouvoir accepter des appels pour le groupe) utilisent Lync 2013 pour se connecter à et se déconnecter du groupe. Si un groupe d’agents est configuré pour les agents formels, les agents cliquent sur un élément de menu dans Lync 2013 pour ouvrir Internet Explorer et afficher une console Web pour se connecter et se déconnecter du groupe.

  - **Services Web**     Les services Web sont requis pour l’outil de configuration de Response Group, la console de connexion et de déconnexion des agents, le panneau de configuration Lync Server et le service Web du client Response Group.

  - Service Web de **client Response Group**     Application Response Group fournit un service Web client, qui peut être utilisé par des applications tierces pour récupérer des informations sur les agents, l’appartenance à un groupe d’agents, l’état de connexion de l’agent, l’état de l’appel pour les groupes et les groupes qui prennent en charge les appels anonymes. Lync 2013 et Lync 2010 attendant utilisent le service Web du client Response Group pour récupérer la liste des groupes Response Group que les agents peuvent utiliser pour effectuer des appels anonymes. Le service web client est installé avec les services web.

</div>

</div>

<span> </span>

</div>

</div>

</div>

