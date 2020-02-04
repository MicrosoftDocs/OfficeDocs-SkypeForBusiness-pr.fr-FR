---
title: 'Lync Server 2013 : Instructions d’intégration de la messagerie unifiée locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f3e57245f0a8edf5b545f9a67547e6be6f63399
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="ff46f-102">Instructions d’intégration de la messagerie unifiée locale et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff46f-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff46f-103">_**Dernière modification de la rubrique :** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="ff46f-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="ff46f-104">Les instructions ci-dessous sont des directives et des pratiques recommandées à envisager lors du déploiement de Voix Entreprise :</span><span class="sxs-lookup"><span data-stu-id="ff46f-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ff46f-105">La messagerie unifiée Exchange prend en charge le protocole IPv6 uniquement si vous utilisez également UCMA 4.</span><span class="sxs-lookup"><span data-stu-id="ff46f-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="ff46f-106">Déploiement d’un serveur Lync Server 2013 Standard Edition ou d’un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="ff46f-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="ff46f-107">Pour plus d’informations sur l’installation, voir [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ff46f-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ff46f-108">Collaborez avec les administrateurs Exchange pour confirmer les tâches que chacun effectuera afin de garantir une intégration réussie en toute transparence.</span><span class="sxs-lookup"><span data-stu-id="ff46f-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="ff46f-109">Déployez les rôles de serveur de boîte aux lettres Exchange dans chaque forêt de messagerie unifiée Exchange dans laquelle vous souhaitez autoriser les utilisateurs pour la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="ff46f-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="ff46f-110">Pour plus d’informations sur l’installation des rôles du serveur Exchange, voir la documentation Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff46f-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ff46f-111">Lorsque la messagerie unifiée (MU) Exchange est installée, elle est configurée pour utiliser un certificat auto-signé.</span><span class="sxs-lookup"><span data-stu-id="ff46f-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="ff46f-112">En revanche, le certificat auto-signé ne permet pas à Lync Server 2013 et à la messagerie unifiée Exchange d’approuver mutuellement, ce qui signifie qu’il est nécessaire de demander un certificat distinct auprès d’une autorité de certification approuvée par les deux serveurs.</span><span class="sxs-lookup"><span data-stu-id="ff46f-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="ff46f-113">Si Lync Server 2013 et la messagerie unifiée Exchange sont installés dans différentes forêts, configurez chaque forêt Exchange pour approuver la forêt Lync Server 2013 et la forêt Lync Server 2013 pour approuver chaque forêt Exchange.</span><span class="sxs-lookup"><span data-stu-id="ff46f-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="ff46f-114">Par ailleurs, définissez les paramètres de messagerie unifiée Exchange des utilisateurs sur les objets utilisateur dans la forêt 2013 du serveur Lync, en général à l’aide d’un script ou d’un outil multiplateforme, tel qu’Identity Lifecycle Manager (ILM).</span><span class="sxs-lookup"><span data-stu-id="ff46f-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="ff46f-115">Si nécessaire, installez la console de gestion Exchange pour gérer vos serveurs de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="ff46f-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="ff46f-116">Procurez-vous des numéros de téléphone valides pour Outlook Voice Access et le standard automatique.</span><span class="sxs-lookup"><span data-stu-id="ff46f-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="ff46f-117">Si vous utilisez une version d’Exchange UM antérieure à Microsoft Exchange Server 2010 Service Pack 1 (SP1), les noms de coordonnées des plans de numérotation URI SIP de messagerie unifiée et les plans de numérotation vocale d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="ff46f-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="ff46f-118">Déploiement de serveurs de messagerie unifiée Exchange redondants :</span><span class="sxs-lookup"><span data-stu-id="ff46f-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ff46f-119">Nous vous recommandons de déployer un minimum de deux serveurs sur lesquels les services de messagerie unifiée Exchange s’exécutent pour chaque plan de numérotation URI SIP Exchange UM que vous configurez pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ff46f-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="ff46f-120">Le déploiement de serveurs redondants fournit non seulement une capacité étendue, mais offre également une disponibilité élevée.</span><span class="sxs-lookup"><span data-stu-id="ff46f-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="ff46f-121">En cas de panne du serveur, Lync Server 2013 peut être configuré pour basculer vers un autre serveur.</span><span class="sxs-lookup"><span data-stu-id="ff46f-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="ff46f-122">Les configurations de l’exemple ci-dessous fournissent la résistance à la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="ff46f-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="ff46f-123">**Exemple 1 : résistance de la messagerie unifiée Exchange**</span><span class="sxs-lookup"><span data-stu-id="ff46f-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="ff46f-124">![Exemple de messagerie unifiée Exchange 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exemple de messagerie unifiée Exchange 1")</span><span class="sxs-lookup"><span data-stu-id="ff46f-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="ff46f-p105">Dans l’exemple 1, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. En cas de défaillance de la messagerie unifiée Exchange dans Tukwila, les enregistrements DNS A pour les serveurs 1 et 2 doivent être configurés de manière à pointer respectivement vers les serveurs 3 et 4. En cas de défaillance de la messagerie unifiée Exchange dans Dublin, les enregistrements DNS A pour les serveurs 3 et 4 doivent être configurés de manière à pointer respectivement vers les serveurs 1 et 2.</span><span class="sxs-lookup"><span data-stu-id="ff46f-p105">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively. In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff46f-128">Pour l’exemple 1, vous devez également affecter l’un des certificats ci-dessous sur chaque serveur de messagerie unifiée Exchange :</span><span class="sxs-lookup"><span data-stu-id="ff46f-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="ff46f-129">Utilisez un certificat avec un caractère générique dans l’autre nom du sujet (SAN).</span><span class="sxs-lookup"><span data-stu-id="ff46f-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="ff46f-130">Ajoutez le nom de domaine complet de chacun des quatre serveurs de messagerie unifiée Exchange dans l’autre nom du sujet.</span><span class="sxs-lookup"><span data-stu-id="ff46f-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="ff46f-131">**Exemple 2 : résistance de la messagerie unifiée Exchange**</span><span class="sxs-lookup"><span data-stu-id="ff46f-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="ff46f-132">![Exemple 2 Exchange UM 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exemple 2 Exchange UM 2")</span><span class="sxs-lookup"><span data-stu-id="ff46f-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="ff46f-p106">Dans l’exemple 2, dans des conditions de fonctionnement normales, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. Les quatre serveurs sont tous inclus dans le plan de numérotation URI SIP des utilisateurs Tukwila, toutefois les serveurs 3 et 4 sont désactivés. Dans le cas d’une défaillance d’un serveur de messagerie unifiée Exchange dans Tukwila, par exemple, les serveurs de messagerie unifiée Exchange 1 et 2 doivent être désactivés et les serveurs de messagerie unifiée Exchange 3 et 4 activés afin que le trafic de messagerie unifiée Exchange Tukwila soit acheminé vers les serveurs dans Dublin.</span><span class="sxs-lookup"><span data-stu-id="ff46f-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="ff46f-136">Pour plus d’informations sur l’activation ou la désactivation de la messagerie unifiée sur Exchange 2013, voir « intégration de la [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)messagerie unifiée Exchange 2013 avec Lync Server ».</span><span class="sxs-lookup"><span data-stu-id="ff46f-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="ff46f-137">Pour plus d’informations sur l’activation ou la désactivation de la messagerie unifiée sur Microsoft Exchange Server 2010, voir :</span><span class="sxs-lookup"><span data-stu-id="ff46f-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="ff46f-138">« Activez la messagerie unifiée sur Exchange 2010 [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)».</span><span class="sxs-lookup"><span data-stu-id="ff46f-138">"Enable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="ff46f-139">« Désactiver la messagerie unifiée sur Exchange 2010 [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)».</span><span class="sxs-lookup"><span data-stu-id="ff46f-139">"Disable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ff46f-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff46f-140">See Also</span></span>


[<span data-ttu-id="ff46f-141">Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff46f-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

