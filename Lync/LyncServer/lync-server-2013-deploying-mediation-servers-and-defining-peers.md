---
title: 'Lync Server 2013 : déploiement des serveurs de médiation et définition des homologues'
description: 'Lync Server 2013 : déploiement des serveurs de médiation et définition des homologues.'
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
ms.openlocfilehash: fc3afce038371920beea1cc52549d8d027429e08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545230"
---
# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Déploiement des serveurs de médiation et définition des homologues dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

La charge de travail voix entreprise, les conférences rendez-vous et les applications avancées de voix entreprise (application Response Group, application de parcage d’appel, contrôle d’admission des appels (CAC), etc.) sont disponibles dans les pools frontaux. Avec Lync Server 2013, la fonctionnalité du serveur de médiation est intégrée au serveur frontal. Un serveur de médiation autonome distinct n’est plus nécessaire. Les pools frontaux peuvent communiquer directement avec les passerelles prises en charge (une passerelle RTC (réseau téléphonique commuté) ou un IP-PBX), ce qui élimine la nécessité d’un serveur de médiation comme intermédiaire.

La seule exception est si vous configurez une jonction SIP pour la connexion à un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet. Pour connecter votre infrastructure voix entreprise à votre fournisseur de jonction SIP, un serveur de médiation distinct doit être déployé.

La connexion entre Lync Server (le composant serveur de médiation sur un pool frontal ou un serveur de médiation autonome) et une passerelle est définie comme une association logique appelée *jonction*. Les rubriques de cette section décrivent comment définir une jonction et déployer un serveur de médiation autonome, si vous vous connectez à une jonction SIP.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Définition d’un serveur de médiation dans le générateur de topologies dans Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Définition d’une passerelle dans le générateur de topologies dans Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Installer les fichiers pour le serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Définir d’autres jonctions dans le générateur de topologies dans Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>Sections connexes

[Configuration de la Conférence rendez-vous dans Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

