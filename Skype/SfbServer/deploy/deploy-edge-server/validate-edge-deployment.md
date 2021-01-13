---
title: Valider votre déploiement Edge dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Résumé : Découvrez comment vérifier que votre déploiement de serveur Edge ou de pool de serveurs Edge fonctionne dans Skype Entreprise Server.'
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804354"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="fbd3d-103">Valider votre déploiement Edge dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="fbd3d-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="fbd3d-104">**Résumé :** Découvrez comment vérifier que votre déploiement de serveur Edge ou de pool de serveurs Edge fonctionne dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="fbd3d-105">Une fois que vous avez déployé votre serveur Edge ou votre pool de serveurs Edge, vous devez savoir s’il fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="fbd3d-106">Voici quelques éléments qui peuvent vous aider à confirmer que votre environnement Edge est connecté à vos serveurs internes et que vos utilisateurs externes peuvent se connecter à votre environnement Skype Entreprise Server via votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="fbd3d-107">Vérifier la connectivité entre vos serveurs internes et vos serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="fbd3d-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="fbd3d-108">Bien que la validation de la connectivité soit effectuée automatiquement dans le serveur Edge ou le pool de serveurs Edge lors de l’installation des serveurs Edge, vous pouvez toujours le confirmer par vous-même avec Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="fbd3d-109">Exécutez l'Get-CsManagementStoreReplicationStatus sur le serveur interne qui dispose du magasin central de gestion ou sur tout ordinateur joint au domaine sur lequel les composants principaux de Skype Entreprise Server (OcsCore.msi) sont installés.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="fbd3d-110">Le résultat initial de l’exécution de cette commande peut donner un état False, plutôt que True, pour la réplication.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-110">The initial result of running this command may give a False status, rather than True, for replication.</span></span> <span data-ttu-id="fbd3d-111">Si cela se produit, exécutez Invoke-CsManagementStoreReplication cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-111">If that happens run the Invoke-CsManagementStoreReplication cmdlet.</span></span> <span data-ttu-id="fbd3d-112">Donnez-lui le temps de terminer la réplication, puis ré-exécutez Get-CsManagementStoreReplicationStatus cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-112">Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="fbd3d-113">Vérifier la connectivité de vos utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="fbd3d-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="fbd3d-114">Nous avons un excellent outil pour confirmer votre configuration de serveur Edge et la possibilité de se connecter, d’envoyer et de recevoir les messages corrects pour les scénarios de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="fbd3d-115">Il s’agit du [site Analyseur de connectivité à distance.](https://testconnectivity.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="fbd3d-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="fbd3d-116">Il s’agit d’un site géré et géré par le Support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="fbd3d-117">Pour utiliser cet outil, accédez au site web et suivez les instructions pour choisir le scénario à votre place.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="fbd3d-118">Éléments à prendre en compte lors du test de la connectivité des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="fbd3d-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="fbd3d-119">Tout test d’accès des utilisateurs externes doit inclure chaque type d’utilisateur interne que votre organisation prend en charge, ce qui peut inclure l’une ou l’ensemble des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fbd3d-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="fbd3d-120">Utilisateurs d’au moins un domaine fédéré (nous vous recommandons toutefois de les tester tous).</span><span class="sxs-lookup"><span data-stu-id="fbd3d-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="fbd3d-121">Utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-121">Anonymous users.</span></span>
    
- <span data-ttu-id="fbd3d-122">Utilisateurs de votre organisation qui sont connectés à distance à Skype Entreprise, mais n’utilisent pas vpn.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="fbd3d-123">Ces tests déterminent si votre serveur Edge est :</span><span class="sxs-lookup"><span data-stu-id="fbd3d-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="fbd3d-124">Écoute sur les ports requis à l’aide d’un client telnet depuis l’extérieur de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="fbd3d-125">Par exemple : telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="fbd3d-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="fbd3d-126">Vous devez effectuer le test précédent sur les ports que vous utilisez sur votre serveur Edge ou votre pool de serveurs Edge, en fonction de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="fbd3d-127">Effectuer une résolution DNS externe précise.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="fbd3d-128">Depuis l’extérieur de votre réseau, testez chacun des FQDN externes de votre serveur Edge ou pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="fbd3d-129">Même si la commande ping échoue, vous verrez les adresses IP, que vous pouvez comparer aux adresses IP que vous avez précédemment affectées.</span><span class="sxs-lookup"><span data-stu-id="fbd3d-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

