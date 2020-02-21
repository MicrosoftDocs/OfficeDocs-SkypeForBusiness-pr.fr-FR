---
title: 'Lync Server 2013 : conditions préalables logicielles pour voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4b0b2e2708abbf3b92223474ec0804c1d11ac8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Conditions préalables logicielles pour voix entreprise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Vérifiez que l’infrastructure dans laquelle vous souhaitez déployer Voix Entreprise respecte les conditions préalables logicielles suivantes :

  - Lync Server 2013 Standard Edition ou Enterprise Edition est installé et opérationnel sur votre réseau.

  - Tous les serveurs Edge sont déployés et opérationnels dans votre réseau de périmètre, y compris les serveurs Edge exécutant le service Edge d’accès, le service Edge A/V, le service Edge de conférence Web et un proxy inverse.

  - Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 ou Microsoft Exchange Server 2013 est requis pour l’intégration de la messagerie unifiée Exchange avec Lync Server et pour fournir des notifications enrichies et des informations de journal des appels au Points de terminaison Lync.

  - Un ou plusieurs utilisateurs ont été créés et activés pour Lync Server.

  - Les clients et appareils Lync ont été correctement déployés.

  - Le générateur de topologies est installé sur un serveur de votre réseau.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>Étapes suivantes : Vérifier les conditions préalables de sécurité et de configuration

Une fois que vous avez vérifié les conditions préalables logicielles pour Voix Entreprise, vous pouvez utiliser la documentation pour poursuivre la préparation du déploiement de Voix Entreprise :

1.  Vérifiez la sécurité, la configuration de l’utilisateur et le matériel préalables, comme décrit dans [Security and configuration Prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Installez le serveur de médiation, comme décrit dans [install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), *uniquement* si vous souhaitez déployer un serveur de médiation ou un pool autonome, car les serveurs de médiation sont installés dans le cadre du processus de déploiement du pool frontal ou du serveur Standard Edition lorsqu’ils sont colocalisés.

3.  Configurez les connexions de jonction pour fournir une connectivité PSTN aux utilisateurs, comme décrit dans la rubrique [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

