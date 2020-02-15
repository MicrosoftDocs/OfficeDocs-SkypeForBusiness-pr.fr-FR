---
title: 'Lync Server 2013 : configuration de la messagerie unifiée sur Microsoft Exchange Server pour qu’elle fonctionne avec Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cbb859a3cd9f49791eb7b959a59c00c38db6336
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41995969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="64750-102">Configuration de la messagerie unifiée sur Microsoft Exchange Server pour qu’elle fonctionne avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64750-102">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64750-103">_**Dernière modification de la rubrique :** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="64750-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="64750-104">Si vous souhaitez utiliser la messagerie unifiée Exchange pour fournir des services de répondeur automatique, Outlook Voice Access ou de standard automatique pour les utilisateurs de voix entreprise, lisez la rubrique <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging Integration in Lync Server 2013</A> dans la documentation de planification, puis suivez les instructions de cette section.</span><span class="sxs-lookup"><span data-stu-id="64750-104">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="64750-105">Pour configurer la messagerie unifiée Exchange de sorte qu’elle fonctionne avec voix entreprise, vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="64750-105">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="64750-106">Configurer des certificats sur le serveur exécutant les services de messagerie unifiée (MU) Exchange</span><span class="sxs-lookup"><span data-stu-id="64750-106">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="64750-107">Ajoutez tous les serveurs d’accès au client et de boîtes aux lettres à tous les plans de numérotation URI SIP de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="64750-107">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="64750-108">Si ce n’est pas le cas, le routage des appels sortants ne fonctionnera pas comme prévu.</span><span class="sxs-lookup"><span data-stu-id="64750-108">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="64750-109">Créez un ou plusieurs plans de numérotation URI SIP de messagerie unifiée, ainsi que les numéros de téléphone d’accès abonné, si nécessaire, puis créez les plans de numérotation Lync Server correspondants.</span><span class="sxs-lookup"><span data-stu-id="64750-109">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="64750-110">Utilisez le script **exchucutil. ps1** pour :</span><span class="sxs-lookup"><span data-stu-id="64750-110">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="64750-111">créer des passerelles IP de messagerie unifiée ;</span><span class="sxs-lookup"><span data-stu-id="64750-111">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="64750-112">créer des groupements de postes de messagerie unifiée ;</span><span class="sxs-lookup"><span data-stu-id="64750-112">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="64750-113">Accordez l’autorisation Lync Server 2013 pour lire les objets des services de domaine Active Directory de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="64750-113">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="64750-114">Créez un objet de standard automatique de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="64750-114">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="64750-115">Créez un objet d’accès abonné.</span><span class="sxs-lookup"><span data-stu-id="64750-115">Create a subscriber access object.</span></span>

  - <span data-ttu-id="64750-116">Créez un URI SIP pour chaque utilisateur et associez les utilisateurs à un plan de numérotation URI SIP de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="64750-116">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="64750-117">Conditions requises et recommandations</span><span class="sxs-lookup"><span data-stu-id="64750-117">Requirements and Recommendations</span></span>

<span data-ttu-id="64750-118">Avant de commencer, la documentation de cette section suppose que vous ayez déployé les rôles Exchange 2013 suivants : accès au client et boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="64750-118">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="64750-119">Dans Microsoft Exchange Server 2013, la messagerie unifiée Exchange s’exécute en tant que service sur ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="64750-119">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="64750-120">Pour plus d’informations sur le déploiement d’Exchange 2013, reportez-vous à la bibliothèque TechNet Exchange 2013 à l’adresse[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="64750-120">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="64750-121">Notez également les points suivants :</span><span class="sxs-lookup"><span data-stu-id="64750-121">Also note the following:</span></span>

  - <span data-ttu-id="64750-122">Si la messagerie unifiée Exchange est installée dans plusieurs forêts, les étapes d’intégration d’Exchange Server doivent être effectuées pour chaque forêt de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="64750-122">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="64750-123">De plus, chaque forêt de messagerie unifiée doit être configurée pour approuver la forêt dans laquelle Lync Server 2013 est déployé, et la forêt dans laquelle Lync Server 2013 est déployé doit être configurée pour approuver chaque forêt de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="64750-123">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="64750-124">Les étapes d’intégration sont effectuées sur les rôles serveur Exchange où les services de messagerie unifiée sont en cours d’exécution et sur le serveur exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64750-124">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="64750-125">Vous devez effectuer les étapes d’intégration de la messagerie unifiée Exchange Server avant d’effectuer les étapes d’intégration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64750-125">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="64750-126">Pour connaître les étapes d’intégration qui sont appliquées aux serveurs et aux rôles d’administrateur, voir <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processus de déploiement pour l’intégration de la messagerie unifiée locale et Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="64750-126">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="64750-127">Les outils suivants doivent être disponibles sur chaque serveur exécutant la messagerie unifiée Exchange :</span><span class="sxs-lookup"><span data-stu-id="64750-127">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="64750-128">Environnement de ligne de commande Exchange Management Shell</span><span class="sxs-lookup"><span data-stu-id="64750-128">Exchange Management Shell</span></span>

  - <span data-ttu-id="64750-129">Le script **exchucutil.ps1**, exécute les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="64750-129">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="64750-130">Il crée une passerelle IP de messagerie unifiée pour chaque Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64750-130">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="64750-131">Il crée un groupement de postes pour chaque passerelle.</span><span class="sxs-lookup"><span data-stu-id="64750-131">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="64750-132">L’identificateur pilote de chaque groupement de postes spécifie le plan de numérotation URI SIP de messagerie unifiée utilisé par le pool frontal ou le serveur Standard Edition Server associé à la passerelle.</span><span class="sxs-lookup"><span data-stu-id="64750-132">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="64750-133">Accorde l’autorisation Lync Server 2013 pour lire les objets de messagerie unifiée Exchange dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="64750-133">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="64750-134">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="64750-134">In This Section</span></span>

  - [<span data-ttu-id="64750-135">Configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="64750-135">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="64750-136">Configuration de la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64750-136">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

