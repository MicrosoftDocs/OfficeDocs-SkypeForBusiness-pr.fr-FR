---
title: Valider votre déploiement Edge dans Skype pour Business Server
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Résumé : Découvrez comment vérifier que votre déploiement de serveur Edge ou pool de serveurs Edge fonctionne dans Skype pour Business Server.'
ms.openlocfilehash: cb239e2777926796761dd91c1460e1147772a34a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21015096"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="f0345-103">Valider votre déploiement Edge dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="f0345-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="f0345-104">**Résumé :** Découvrez comment vérifier que votre déploiement de serveur Edge ou pool de serveurs Edge fonctionne dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="f0345-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="f0345-105">Une fois que vous avez déployé votre serveur Edge ou le pool de serveurs Edge, vous devez savoir si elle fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="f0345-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="f0345-106">Voici quelques éléments qui peuvent aider à vous demandant de confirmer votre environnement Edge est connecté à vos serveurs internes et que vos utilisateurs externes peuvent se connecter à votre Skype pour un environnement Business Server, par le biais de votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="f0345-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="f0345-107">Vérification de la connectivité entre vos serveurs internes et vos serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="f0345-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="f0345-108">Alors que la validation de la connectivité est effectuée automatiquement au serveur Edge ou pool de serveurs Edge lorsque les serveurs de périphérie sont installés, vous pouvez toujours confirmer par vous-même avec Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0345-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="f0345-109">Exécutez l’applet de commande Get-CsManagementStoreReplicationStatus sur le serveur interne ayant magasin Central de gestion, ou n’importe quel ordinateur du domaine jointes sur le Skype pour Business Server les composants principaux (OcsCore.msi) sont installés.</span><span class="sxs-lookup"><span data-stu-id="f0345-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="f0345-p103">Le résultat initial de l’exécution de cette commande peut donner un statut False, plutôt que True, pour la réplication. Dans ce cas, exécutez l’applet de commande Invoke-Cs ManagementStoreReplication. Donnez-lui un peu de temps pour terminer la réplication, puis, exécutez à nouveau l’applet de commande Get-Cs ManagementStoreReplicationStatus.</span><span class="sxs-lookup"><span data-stu-id="f0345-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="f0345-113">Vérification de la connectivité pour vos utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="f0345-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="f0345-114">Nous avons un excellent outil pour confirmer la configuration de votre serveur Edge et la possibilité de se connecter, envoyer et recevoir les messages corrects pour les scénarios de serveur de transport Edge.</span><span class="sxs-lookup"><span data-stu-id="f0345-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="f0345-115">Il s’agit du [site Anaylzer de connectivité à distance](https://testconnectivity.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f0345-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="f0345-116">Il s’agit d’un site géré par le service Support technique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f0345-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="f0345-117">Pour utiliser cet outil, accédez au site web et suivez les instructions pour choisir le scénario adéquat pour vous.</span><span class="sxs-lookup"><span data-stu-id="f0345-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="f0345-118">Éléments à prendre en compte lors du test de connectivité des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="f0345-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="f0345-119">N’importe quel test pour l’accès des utilisateurs externes doit inclure tous les types d’utilisateurs internes que votre organisation prend en charge, ce qui peut inclure une ou toutes les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f0345-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="f0345-120">Utilisateurs d’au moins un domaine fédéré (nous vous recommandons de les tester toutes quand même)</span><span class="sxs-lookup"><span data-stu-id="f0345-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="f0345-121">Utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="f0345-121">Anonymous users.</span></span>
    
- <span data-ttu-id="f0345-122">Utilisateurs de votre organisation qui sont connectés à Skype pour les entreprises à distance, mais ne sont pas à l’aide de VPN.</span><span class="sxs-lookup"><span data-stu-id="f0345-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="f0345-123">Ces tests déterminera si votre serveur Edge est :</span><span class="sxs-lookup"><span data-stu-id="f0345-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="f0345-124">Écoute sur les ports requis à l’aide d’un client telnet depuis l’extérieur de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="f0345-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="f0345-125">Par exemple : telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="f0345-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="f0345-126">Vous devez effectuer le test précédent sur les ports que vous utilisez sur votre serveur Edge ou le pool de serveurs Edge, en fonction de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="f0345-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="f0345-127">Effectuer une résolution DNS externe précise.</span><span class="sxs-lookup"><span data-stu-id="f0345-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="f0345-128">À partir de l’extérieur de votre réseau, une commande ping chacun des noms de domaines complets externes de votre serveur Edge ou le pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="f0345-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="f0345-129">Même si la commande ping échoue, vous verrez les adresses IP que vous pouvez comparer les adresses IP que vous avez précédemment assigné.</span><span class="sxs-lookup"><span data-stu-id="f0345-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

