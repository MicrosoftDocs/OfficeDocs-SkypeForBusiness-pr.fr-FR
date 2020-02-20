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
ms.openlocfilehash: 36ec427751fc6593f03af11bfecddf3bd0bb6280
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="62f10-102">Conditions préalables logicielles pour voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62f10-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62f10-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="62f10-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="62f10-104">Vérifiez que l’infrastructure dans laquelle vous souhaitez déployer Voix Entreprise respecte les conditions préalables logicielles suivantes :</span><span class="sxs-lookup"><span data-stu-id="62f10-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="62f10-105">Lync Server 2013 Standard Edition ou Enterprise Edition est installé et opérationnel sur votre réseau.</span><span class="sxs-lookup"><span data-stu-id="62f10-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="62f10-106">Tous les serveurs Edge sont déployés et opérationnels dans votre réseau de périmètre, y compris les serveurs Edge exécutant le service Edge d’accès, le service Edge A/V, le service Edge de conférence Web et un proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="62f10-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="62f10-107">Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 ou Microsoft Exchange Server 2013 est requis pour l’intégration de la messagerie unifiée Exchange avec Lync Server et pour fournir des notifications enrichies et des informations de journal des appels au Points de terminaison Lync.</span><span class="sxs-lookup"><span data-stu-id="62f10-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="62f10-108">Un ou plusieurs utilisateurs ont été créés et activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62f10-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="62f10-109">Les clients et appareils Lync ont été correctement déployés.</span><span class="sxs-lookup"><span data-stu-id="62f10-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="62f10-110">Le générateur de topologies est installé sur un serveur de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="62f10-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="62f10-111">Étapes suivantes : Vérifier les conditions préalables de sécurité et de configuration</span><span class="sxs-lookup"><span data-stu-id="62f10-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="62f10-112">Une fois que vous avez vérifié les conditions préalables logicielles pour Voix Entreprise, vous pouvez utiliser la documentation pour poursuivre la préparation du déploiement de Voix Entreprise :</span><span class="sxs-lookup"><span data-stu-id="62f10-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="62f10-113">Vérifiez la sécurité, la configuration de l’utilisateur et le matériel préalables, comme décrit dans [Security and configuration Prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="62f10-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="62f10-114">Installez le serveur de médiation, comme décrit dans [install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), *uniquement* si vous souhaitez déployer un serveur de médiation ou un pool autonome, car les serveurs de médiation sont installés dans le cadre du processus de déploiement du pool frontal ou du serveur Standard Edition lorsqu’ils sont colocalisés.</span><span class="sxs-lookup"><span data-stu-id="62f10-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="62f10-115">Configurez les connexions de jonction pour fournir une connectivité PSTN aux utilisateurs, comme décrit dans la rubrique [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="62f10-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

