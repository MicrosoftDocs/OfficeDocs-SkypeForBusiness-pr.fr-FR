---
title: Déploiement de l’outil SEFAUtil dans Skype pour les entreprises
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Déploiement de l’outil SEFAUtil dans Skype pour Business Server.
ms.openlocfilehash: 64319438604e30ab7187885eb82daf554d176917
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223083"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="3c5c0-103">Déploiement de l’outil SEFAUtil dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="3c5c0-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="3c5c0-104">Déploiement de l’outil SEFAUtil dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="3c5c0-105">Pour déployer et gérer la collecte d’appel de groupe, vous devez utiliser le Skype pour la version de l’outil SEFAUtil Business Server.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3c5c0-106">Exécution de Microsoft Unified Communications Managed API (UCMA) 5 doit être installée sur tout ordinateur où vous prévoyez d’exécuter l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="3c5c0-107">Télécharger ici : [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="3c5c0-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="3c5c0-108">Vous pouvez également télécharger le SDK UCMA 5, qui inclut le runtime ici : [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="3c5c0-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="3c5c0-109">Vous pouvez exécuter l’outil SEFAUtil dans n’importe quel pool frontal dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="3c5c0-110">Pour exécuter l’outil SEFAUtil, vous devez exécuter les étapes 1, 2 et 3 depuis le Skype pour l’Assistant de déploiement d’entreprise sur l’ordinateur d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="3c5c0-111">SEFAUtil requiert le magasin de configurations local à présent, ainsi que d’un certificat.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3c5c0-112">Pour plus d’informations sur l’exécution de SEFAUtil, voir l’article de blog, «[comment obtenir SEFAutil en cours d’exécution ?](https://go.microsoft.com/fwlink/?LinkId=278940)».</span><span class="sxs-lookup"><span data-stu-id="3c5c0-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="3c5c0-113">Pour déployer SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3c5c0-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="3c5c0-114">Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires comme indiqué dans **Déléguer des autorisations d’installation**.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="3c5c0-115">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3c5c0-116">L’outil SEFAUtil ne peut être exécuté que sur un ordinateur qui fait partie d’un pool d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="3c5c0-117">Si nécessaire, définir un pool d’applications approuvées pour le pool frontal où vous prévoyez d’exécuter SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="3c5c0-118">Sur la ligne de commande, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3c5c0-118">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="3c5c0-119">Nom de domaine complet de pool : Nom de domaine complet du serveur ou du pool qui hébergera l’application SEFAUtil (généralement un Skype pour le serveur frontal métiers ou du pool).</span><span class="sxs-lookup"><span data-stu-id="3c5c0-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="3c5c0-120">Registrar nom de domaine complet de pool : Nom de domaine complet de le Skype pour Business frontal ou pool associé à ce pool d’applications.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="3c5c0-121">Site de pool : L’ID de Site du site sur lequel ce pool est hébergé.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="3c5c0-p105">Définissez l’outil SEFAUtil en tant qu’application approuvée. Sur la ligne de commande, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3c5c0-p105">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="3c5c0-124">Vous pouvez utiliser un autre port si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="3c5c0-p106">Activez la topologie avec vos modifications. Sur la ligne de commande, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3c5c0-p106">Enable the topology with your changes. At the command line, run:</span></span>
    
   ```
   Enable-CsTopology
   ```

6. <span data-ttu-id="3c5c0-127">Si vous n’avez pas déjà, téléchargez le Skype pour la version de l’outil SEFAUtil Business Server à partir de [cet emplacement](https://www.microsoft.com/en-us/download/details.aspx?id=52631)et les installer sur le pool d’applications approuvées créé à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="3c5c0-128">Vérifiez que l’outil SEFAUtil s’exécute correctement ainsi :</span><span class="sxs-lookup"><span data-stu-id="3c5c0-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="3c5c0-129">a.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-129">a.</span></span> <span data-ttu-id="3c5c0-130">Exécutez l’outil à partir de l’invite de commande Windows avec des droits d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="3c5c0-131">b.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-131">b.</span></span> <span data-ttu-id="3c5c0-132">Affichez les paramètres de transfert d’appel d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="3c5c0-133">Sur la ligne de commande, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3c5c0-133">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="3c5c0-134">Les paramètres de transfert d’appel de l’utilisateur s’afficheront.</span><span class="sxs-lookup"><span data-stu-id="3c5c0-134">The call forwarding settings for the user will be displayed.</span></span>
    

