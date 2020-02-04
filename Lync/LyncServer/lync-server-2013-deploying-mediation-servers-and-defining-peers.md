---
title: 'Lync Server 2013 : Déploiement des serveurs de médiation et définition des homologues'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b20f5e733dddd34971ca3a5070e99364785e147a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Déploiement des serveurs de médiation et définition des homologues dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

La charge de travail voix entreprise, les conférences rendez-vous et les applications Advanced Enterprise voix (application de groupe de réponse, application de stationnement d’appel, contrôle d’admission des appels (CAC), etc.), sont disponibles dans des regroupements front-end. Avec Lync Server 2013, les fonctionnalités du serveur de médiation sont intégrées au serveur frontal. Un serveur de médiation autonome distinct n’est plus nécessaire. Les pools front-end peuvent communiquer directement avec les passerelles prises en charge (une passerelle RTC (réseau téléphonique commuté) ou un PBX IP (PBX), ce qui évite qu’un serveur de médiation ne serve de intermédiaire.

La seule exception est si vous configurez une jonction SIP (Session Initiation Protocol) pour la connexion à un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet. Pour connecter l’infrastructure vocale de votre entreprise à votre fournisseur SIP Trunk, un serveur de médiation distinct doit être déployé.

La connexion entre Lync Server (le composant du serveur de médiation sur une liste frontale ou un serveur de médiation autonome) et une passerelle est définie en tant qu’association logique appelée *Trunk*. Les rubriques de cette section expliquent comment définir un élément Trunk et comment déployer un serveur de médiation autonome si vous vous connectez à un Trunk SIP.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Définir un serveur de médiation dans le générateur de topologies de Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Définir une passerelle dans le générateur de topologies de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Installer les fichiers pour le serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Définir des lignes supplémentaires dans le générateur de topologies de Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>Sections associées

[Configuration de conférences rendez-vous dans Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

