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

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="a167c-102">Configuration logicielle requise pour Entreprise Voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a167c-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a167c-103">_**Dernière modification de la rubrique:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a167c-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a167c-104">Vérifiez que l’infrastructure dans laquelle vous envisagez de déployer Enterprise Voice remplit les conditions logicielles suivantes:</span><span class="sxs-lookup"><span data-stu-id="a167c-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="a167c-105">Lync Server 2013 Standard Edition ou Enterprise Edition est installé et opérationnel sur votre réseau.</span><span class="sxs-lookup"><span data-stu-id="a167c-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="a167c-106">Tous les serveurs Edge sont déployés et opérationnels dans votre réseau de périmètre, y compris les serveurs Edge exécutant le service Edge d’accès, le service Edge A/V, le service Edge de conférence Web et un proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a167c-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="a167c-107">Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 ou Microsoft Exchange Server 2013 est requis pour l’intégration de la messagerie unifiée Exchange avec Lync Server et la fourniture de notifications complètes et de journaux d’appels vers le Points de terminaison Lync.</span><span class="sxs-lookup"><span data-stu-id="a167c-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="a167c-108">Un ou plusieurs utilisateurs ont été créés et activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a167c-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="a167c-109">Les clients et appareils Lync ont été déployés avec succès.</span><span class="sxs-lookup"><span data-stu-id="a167c-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="a167c-110">Le générateur de topologie est installé sur un serveur de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="a167c-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="a167c-111">Étapes suivantes: vérifier la configuration requise pour la sécurité et la configuration</span><span class="sxs-lookup"><span data-stu-id="a167c-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="a167c-112">Après vérification de la configuration logicielle requise pour Enterprise Voice, vous pouvez utiliser la documentation pour continuer à préparer le déploiement d’Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="a167c-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="a167c-113">Vérifiez la sécurité, la configuration de l’utilisateur et le matériel perquisites, comme décrit dans la section [sécurité et configuration requise pour Enterprise Voice dans Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="a167c-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="a167c-114">Installez le serveur de médiation, comme décrit dans [la rubrique installer les fichiers pour le serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), mais *uniquement* si vous voulez déployer un serveur ou un pool de médiation autonome, car les serveurs de médiation sont installés dans le cadre du pool frontal ou Processus de déploiement d’un serveur Standard Edition lorsqu’il est localisé.</span><span class="sxs-lookup"><span data-stu-id="a167c-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="a167c-115">Configurez les connexions de Trunk pour fournir une connectivité PSTN aux utilisateurs, comme décrit dans la rubrique [Configuration des Trunks dans Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="a167c-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

