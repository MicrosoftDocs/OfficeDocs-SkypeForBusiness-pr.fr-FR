---
title: 'Lync Server 2013 : Configuration logicielle requise pour Entreprise Voix'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac981d7a30a85d25d2dfb376cfa34f812e898bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Configuration logicielle requise pour Entreprise Voix dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-03_

Vérifiez que l’infrastructure dans laquelle vous envisagez de déployer Enterprise Voice remplit les conditions logicielles suivantes:

  - Lync Server 2013 Standard Edition ou Enterprise Edition est installé et opérationnel sur votre réseau.

  - Tous les serveurs Edge sont déployés et opérationnels dans votre réseau de périmètre, y compris les serveurs Edge exécutant le service Edge d’accès, le service Edge A/V, le service Edge de conférence Web et un proxy inverse.

  - Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 ou Microsoft Exchange Server 2013 est requis pour l’intégration de la messagerie unifiée Exchange avec Lync Server et la fourniture de notifications complètes et de journaux d’appels vers le Points de terminaison Lync.

  - Un ou plusieurs utilisateurs ont été créés et activés pour Lync Server.

  - Les clients et appareils Lync ont été déployés avec succès.

  - Le générateur de topologie est installé sur un serveur de votre réseau.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>Étapes suivantes: vérifier la configuration requise pour la sécurité et la configuration

Après vérification de la configuration logicielle requise pour Enterprise Voice, vous pouvez utiliser la documentation pour continuer à préparer le déploiement d’Enterprise Voice:

1.  Vérifiez la sécurité, la configuration de l’utilisateur et le matériel perquisites, comme décrit dans la section [sécurité et configuration requise pour Enterprise Voice dans Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Installez le serveur de médiation, comme décrit dans [la rubrique installer les fichiers pour le serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), mais *uniquement* si vous voulez déployer un serveur ou un pool de médiation autonome, car les serveurs de médiation sont installés dans le cadre du pool frontal ou Processus de déploiement d’un serveur Standard Edition lorsqu’il est localisé.

3.  Configurez les connexions de Trunk pour fournir une connectivité PSTN aux utilisateurs, comme décrit dans la rubrique [Configuration des Trunks dans Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

