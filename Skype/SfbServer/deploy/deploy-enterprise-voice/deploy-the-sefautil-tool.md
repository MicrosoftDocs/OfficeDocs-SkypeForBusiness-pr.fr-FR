---
title: Déploiement de l’outil SEFAUtil dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Déploiement de l’outil SEFAUtil dans Skype entreprise Server.
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986809"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="a5bb3-103">Déploiement de l’outil SEFAUtil dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="a5bb3-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="a5bb3-104">Déploiement de l’outil SEFAUtil dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="a5bb3-105">Pour déployer et gérer la prise d’appel de groupe, vous devez utiliser la version Skype entreprise Server de l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a5bb3-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime doit être installé sur tout ordinateur sur lequel vous envisagez d’exécuter l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="a5bb3-107">Téléchargez-le ici : [Unified Communications Managed API 5,0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="a5bb3-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="a5bb3-108">Vous pouvez également télécharger le kit de développement logiciel (SDK) UCMA 5, qui inclut le runtime, ici : [UCMA 5,0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="a5bb3-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="a5bb3-109">Vous pouvez exécuter l’outil SEFAUtil dans n’importe quel pool frontal de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="a5bb3-110">Pour exécuter l’outil SEFAUtil, vous devez exécuter les étapes 1, 2 et 3 de l’Assistant Déploiement de Skype entreprise sur l’ordinateur d’application approuvé.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="a5bb3-111">SEFAUtil nécessite que le magasin de configuration local soit présent, ainsi qu’un certificat.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5bb3-112">Pour plus d’informations sur l’exécution d’SEFAUtil, consultez l’article du blog «[How to get SEFAUtil Running ?](https://go.microsoft.com/fwlink/?LinkId=278940)».</span><span class="sxs-lookup"><span data-stu-id="a5bb3-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="a5bb3-113">Pour déployer SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="a5bb3-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="a5bb3-114">Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans **Delegate Setup permissions**.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="a5bb3-115">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a5bb3-116">L’outil SEFAUtil peut être exécuté uniquement sur un ordinateur qui fait partie d’un pool d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="a5bb3-117">Si nécessaire, définissez un pool d’applications approuvées pour le pool frontal dans lequel vous prévoyez d’exécuter SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="a5bb3-118">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a5bb3-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="a5bb3-119">Nom de domaine complet du pool : nom de domaine complet (FQDN) du serveur ou du pool qui hébergera l’application SEFAUtil (généralement un serveur ou un pool de serveurs frontaux Skype entreprise).</span><span class="sxs-lookup"><span data-stu-id="a5bb3-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="a5bb3-120">Nom de domaine complet du serveur d’inscriptions de pool : nom de domaine complet du serveur ou pool de serveurs frontaux Skype entreprise associé à ce pool d’applications.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="a5bb3-121">Site de pool : ID de site du site sur lequel ce pool est hébergé.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="a5bb3-122">Définissez l’outil SEFAUtil en tant qu’application approuvée.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="a5bb3-123">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a5bb3-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="a5bb3-124">Vous pouvez utiliser un autre port si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="a5bb3-125">Activez la topologie avec vos modifications.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-125">Enable the topology with your changes.</span></span> <span data-ttu-id="a5bb3-126">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a5bb3-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="a5bb3-127">Si vous ne l’avez pas encore fait, téléchargez la version de Skype entreprise Server de l’outil SEFAUtil à partir de [cet emplacement](https://www.microsoft.com/download/details.aspx?id=52631)et installez-la sur le pool d’applications approuvées que vous avez créé à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="a5bb3-128">Vérifiez que l’outil SEFAUtil s’exécute correctement, comme suit :</span><span class="sxs-lookup"><span data-stu-id="a5bb3-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="a5bb3-129">a.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-129">a.</span></span> <span data-ttu-id="a5bb3-130">Exécutez l’outil à partir de l’invite de commandes Windows avec les privilèges d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="a5bb3-131">b.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-131">b.</span></span> <span data-ttu-id="a5bb3-132">Afficher les paramètres de transfert d’appel d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="a5bb3-133">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a5bb3-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="a5bb3-134">Les paramètres de transfert d’appel de l’utilisateur seront affichés.</span><span class="sxs-lookup"><span data-stu-id="a5bb3-134">The call forwarding settings for the user will be displayed.</span></span>
    

