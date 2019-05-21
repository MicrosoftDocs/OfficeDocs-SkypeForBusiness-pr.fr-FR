---
title: Valider votre déploiement Edge dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Résumé: Découvrez comment vérifier que votre déploiement du serveur Edge Server ou du pool de serveurs Edge fonctionne dans Skype entreprise Server.'
ms.openlocfilehash: 0c432cba78e97add71bb7c4e21e155f92c9fe66a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306887"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="757e4-103">Valider votre déploiement Edge dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="757e4-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="757e4-104">**Résumé:** Découvrez comment vérifier que votre déploiement du serveur Edge Server ou du pool de serveurs Edge fonctionne dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="757e4-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="757e4-105">Après avoir déployé votre serveur Edge Server ou le pool de serveurs Edge, vous devez savoir s’il fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="757e4-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="757e4-106">Voici quelques conseils qui peuvent vous aider à confirmer la connexion de votre environnement Edge à vos serveurs internes et à la connexion de vos utilisateurs externes à votre environnement Skype entreprise Server via votre périphérie.</span><span class="sxs-lookup"><span data-stu-id="757e4-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="757e4-107">Vérification de la connectivité entre vos serveurs internes et vos serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="757e4-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="757e4-108">Lorsque la validation de la connectivité est effectuée automatiquement dans un serveur Edge ou un pool de serveurs Edge lorsque les serveurs de périphérie sont installés, vous pouvez toujours confirmer cela avec Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="757e4-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="757e4-109">Exécutez l’applet de construction Get-CsManagementStoreReplicationStatus sur le serveur interne, qui dispose de la Banque centrale de gestion ou de n’importe quel ordinateur sur lequel sont installés les composants principaux de Skype entreprise Server (OcsCore. msi).</span><span class="sxs-lookup"><span data-stu-id="757e4-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="757e4-p103">Le résultat initial de l’exécution de cette commande peut donner un statut False, plutôt que True, pour la réplication. Dans ce cas, exécutez l’applet de commande Invoke-Cs ManagementStoreReplication. Donnez-lui un peu de temps pour terminer la réplication, puis, exécutez à nouveau l’applet de commande Get-Cs ManagementStoreReplicationStatus.</span><span class="sxs-lookup"><span data-stu-id="757e4-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="757e4-113">Vérification de la connectivité pour vos utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="757e4-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="757e4-114">Nous avons un excellent outil pour confirmer la configuration de votre serveur Edge et la possibilité de vous connecter, d’envoyer et de recevoir les messages appropriés pour les scénarios de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="757e4-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="757e4-115">Il s’agit du [site Anaylzer de connexion à distance](https://testconnectivity.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="757e4-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="757e4-116">Il s’agit d’un site géré par le service Support technique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="757e4-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="757e4-117">Pour utiliser cet outil, accédez au site web et suivez les instructions pour choisir le scénario adéquat pour vous.</span><span class="sxs-lookup"><span data-stu-id="757e4-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="757e4-118">Éléments à prendre en compte lors du test de connectivité des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="757e4-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="757e4-119">N’importe quel test pour l’accès des utilisateurs externes doit inclure tous les types d’utilisateurs internes que votre organisation prend en charge, ce qui peut inclure une ou toutes les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="757e4-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="757e4-120">Utilisateurs d’au moins un domaine fédéré (nous vous recommandons de les tester toutes quand même)</span><span class="sxs-lookup"><span data-stu-id="757e4-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="757e4-121">Utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="757e4-121">Anonymous users.</span></span>
    
- <span data-ttu-id="757e4-122">Les utilisateurs de votre organisation qui sont connectés à Skype entreprise à distance, mais qui ne fonctionnent pas avec VPN.</span><span class="sxs-lookup"><span data-stu-id="757e4-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="757e4-123">Ces tests déterminent si votre serveur Edge est:</span><span class="sxs-lookup"><span data-stu-id="757e4-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="757e4-124">Écoute sur les ports requis à l’aide d’un client telnet depuis l’extérieur de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="757e4-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="757e4-125">Par exemple : telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="757e4-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="757e4-126">Selon votre déploiement, vous devez effectuer le test précédent sur les ports que vous utilisez sur votre serveur Edge ou sur le pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="757e4-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="757e4-127">Effectuer une résolution DNS externe précise.</span><span class="sxs-lookup"><span data-stu-id="757e4-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="757e4-128">À partir de l’extérieur de votre réseau, effectuez un test ping sur chacun des noms de domaine complets externes du serveur Edge ou du pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="757e4-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="757e4-129">Même si le test échoue, vous verrez les adresses IP, qui vous permettent de comparer les adresses IP que vous avez précédemment affectées.</span><span class="sxs-lookup"><span data-stu-id="757e4-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

