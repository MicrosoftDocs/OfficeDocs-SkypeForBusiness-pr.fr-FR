---
title: Validation du déploiement d’Edge dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Résumé : Apprenez à vérifier que votre déploiement de serveur Edge ou d’un pool de serveur de transport Edge fonctionne dans Skype pour Business Server 2015.'
ms.openlocfilehash: 02f909310e6b491ae97e31b7013b1307c7688ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server-2015"></a><span data-ttu-id="82db7-103">Validation du déploiement d’Edge dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="82db7-103">Validate your Edge deployment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="82db7-104">**Résumé :** Découvrez comment vérifier que votre déploiement de serveur Edge ou d’un pool de serveur de transport Edge fonctionne dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="82db7-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="82db7-105">Une fois que vous avez déployé votre serveur Edge ou un pool de serveur de transport Edge, vous devez savoir si elle fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="82db7-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="82db7-106">Voici quelques éléments qui peut vous aider à confirmer votre environnement de bord est connectée à vos serveurs internes, ainsi que vos utilisateurs externes peuvent se connecter à votre Skype pour environnement d’entreprise serveur 2015, passant par le bord.</span><span class="sxs-lookup"><span data-stu-id="82db7-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server 2015 environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="82db7-107">Vérification de la connectivité entre vos serveurs internes et vos serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="82db7-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="82db7-108">Lors de la validation de la connectivité est effectuée automatiquement dans le serveur de transport Edge ou d’un pool de serveur de transport Edge lorsque les serveurs périphériques sont installés, vous pouvez toujours vérifier par vous-même avec Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82db7-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="82db7-109">Exécutez l’applet de commande Get-CsManagementStoreReplicationStatus sur le serveur interne qui a la direction centrale de stocker ou de n’importe quel ordinateur faisant partie de domaine sur lequel Skype pour composants de base 2015 Business Server (OcsCore.msi) sont installés.</span><span class="sxs-lookup"><span data-stu-id="82db7-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server 2015 Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="82db7-p103">Le résultat initial de l’exécution de cette commande peut donner un statut False, plutôt que True, pour la réplication. Dans ce cas, exécutez l’applet de commande Invoke-Cs ManagementStoreReplication. Donnez-lui un peu de temps pour terminer la réplication, puis, exécutez à nouveau l’applet de commande Get-Cs ManagementStoreReplicationStatus.</span><span class="sxs-lookup"><span data-stu-id="82db7-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="82db7-113">Vérification de la connectivité pour vos utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="82db7-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="82db7-114">Nous avons un excellent outil pour la confirmation de votre configuration de serveur de transport Edge et de la possibilité de se connecter, d’envoyer et de recevoir les messages appropriés pour les scénarios de serveur de transport Edge.</span><span class="sxs-lookup"><span data-stu-id="82db7-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="82db7-115">Il s’agit du [site de Anaylzer de connectivité à distance](https://testconnectivity.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="82db7-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="82db7-116">Il s’agit d’un site géré par le service Support technique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="82db7-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="82db7-117">Pour utiliser cet outil, accédez au site web et suivez les instructions pour choisir le scénario adéquat pour vous.</span><span class="sxs-lookup"><span data-stu-id="82db7-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="82db7-118">Éléments à prendre en compte lors du test de connectivité des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="82db7-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="82db7-119">N’importe quel test pour l’accès des utilisateurs externes doit inclure tous les types d’utilisateurs internes que votre organisation prend en charge, ce qui peut inclure une ou toutes les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="82db7-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="82db7-120">Utilisateurs d’au moins un domaine fédéré (nous vous recommandons de les tester toutes quand même)</span><span class="sxs-lookup"><span data-stu-id="82db7-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="82db7-121">Utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="82db7-121">Anonymous users.</span></span>
    
- <span data-ttu-id="82db7-122">Utilisateurs de votre organisation à distance connectés dans Skype pour les entreprises, mais qui ne sont pas à l’aide de VPN.</span><span class="sxs-lookup"><span data-stu-id="82db7-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="82db7-123">Ces tests détermine si votre serveur de transport Edge est :</span><span class="sxs-lookup"><span data-stu-id="82db7-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="82db7-124">Écoute sur les ports requis à l’aide d’un client telnet depuis l’extérieur de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="82db7-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="82db7-125">Par exemple : telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="82db7-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="82db7-126">Vous devez effectuer le test précédent sur les ports que vous utilisez sur votre serveur de transport Edge ou d’un pool de serveur de transport Edge, en fonction de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="82db7-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="82db7-127">Effectuer une résolution DNS externe précise.</span><span class="sxs-lookup"><span data-stu-id="82db7-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="82db7-128">À partir d’à l’extérieur de votre réseau, exécutez ping sur chaque les FQDN externes de votre serveur de transport Edge ou de pool de serveur de transport Edge.</span><span class="sxs-lookup"><span data-stu-id="82db7-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="82db7-129">Même si la commande ping échoue, vous verrez les adresses IP, ce qui vous pouvez de comparer les adresses IP que vous avez précédemment affecté.</span><span class="sxs-lookup"><span data-stu-id="82db7-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

