---
title: 'Lync Server 2013 : Composants utilisés par Response Group'
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
ms.openlocfilehash: 81275ca027971d661d3323fbfc175c51d4f4d7d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Composants utilisés par Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-11_

L’application Response Group est activée automatiquement lorsque vous déployez Enterprise Voice. Cette section décrit les composants qui prennent en charge l’application Response Group.

<div>

## <a name="response-group-components"></a>Composants de Response Group

Les composants Microsoft Lync Server 2013 suivants prennent en charge l’application Response Group :

  - ****   Le service d’application de service d’application fournit une plateforme de déploiement, d’hébergement et de gestion d’applications de communications unifiées, telles que Response Group. Le service d’application est automatiquement installé sur chaque serveur frontal d’une grappe frontale et sur tous les serveurs Standard Edition Server.

  - **Application de Response Group**   l’application Response Group est l’une des applications de communications unifiées hébergées par le service d’application. Elle est incluse automatiquement lorsque vous déployez Response Group. Le Response Group application route et met en file d’attente les appels entrants vers des groupes d’agents.

  - **Module**   linguistique un module linguistique est requis pour la prise en charge de la reconnaissance vocale et de la synthèse vocale. Ces technologies vocales servent lors de la configuration de messages (message de bienvenue et autres messages, ou les questions et réponses du système de réponse vocale interactive, par exemple). Par défaut, les 26 modules linguistiques pris en charge sont installés lors du déploiement de Lync Server 2013.

  - **Les fichiers audio sont**utilisés pour les messages et la musique en attente.   

  - ****   Le groupe de réponse du magasin de fichiers utilise le magasin de fichiers pour stocker des fichiers audio. Plusieurs pools de groupe de réponse peuvent utiliser la même instance du magasin de fichiers.

  - **Outil de configuration de Response Group**   l’outil de configuration de Response Group est un outil Web utilisé pour créer et configurer des groupes de réponse. L’outil de configuration de Response Group est inclus dans l’installation des services Web.

  - **Panneau de configuration Microsoft Lync Server 2013**   vous pouvez utiliser le panneau de configuration de Lync Server pour configurer et configurer des groupes d’agents et des files d’attente pour les groupes de réponses.

  - **Lync Server Management Shell**   tous les paramètres de groupe de réponse peuvent être configurés à l’aide d’applets de applet Lync Server Management Shell.

  - **Microsoft Lync 2013**   -agents officiels (agents nécessaires pour se connecter au groupe avant de pouvoir accepter les appels pour le groupe) utilisez Lync 2013 pour vous connecter et vous déconnecter du groupe. Si un groupe d’agent est configuré pour les agents officiels, les agents cliquent sur un élément de menu dans Lync 2013 pour ouvrir Internet Explorer et afficher une console de pages Web pour se connecter et s’en déconnecter.

  - ****   Les services Web services Web sont requis pour les outils de configuration de Response Group, la console de connexion et de connexion des agents, le panneau de configuration de Lync Server et le service Web du client de Response Group.

  - ****   Response Group Response service Web application de Response Group fournit un service Web client qui peut être utilisé par des applications tierces pour récupérer des informations sur les agents, l’appartenance aux groupes d’agents, l’état de connexion des agents, le statut des appels pour les groupes et les groupes qui prennent en charge les appels anonymes. Lync 2013 et Lync 2010 attendant utiliser le service Web du client de Response Group pour récupérer la liste des groupes de réponses que les agents peuvent utiliser pour effectuer des appels anonymes. Le service Web client est inclus dans le cadre de l’installation des services Web.

</div>

</div>

<span> </span>

</div>

</div>

</div>

