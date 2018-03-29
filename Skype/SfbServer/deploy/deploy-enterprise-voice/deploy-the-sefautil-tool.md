---
title: Déploiement de l’outil SEFAUtil dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Déploiement de l’outil SEFAUtil dans Skype pour Business Server.
ms.openlocfilehash: eba4c6d9c6d0c48256621537350a822c3314ca40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a><span data-ttu-id="49de8-103">Déploiement de l’outil SEFAUtil dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="49de8-103">Deploy the SEFAUtil tool in Skype for Business 2015</span></span>
 
<span data-ttu-id="49de8-104">Déploiement de l’outil SEFAUtil dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="49de8-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="49de8-105">Pour déployer et gérer la collecte de groupe appeler, vous devez utiliser le Skype pour la version de serveur d’entreprise de l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="49de8-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="49de8-106">Le Kit de développement logiciel (SDK) Microsoft Unified Communications Managed API (UCMA) 3.0 Core doit être sur les ordinateurs sur lesquels vous voulez exécuter l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="49de8-106">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> 
  
<span data-ttu-id="49de8-107">Vous pouvez exécuter l’outil SEFAUtil dans n’importe quel pool frontal dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="49de8-107">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="49de8-108">Pour plus d’informations sur l’exécution de SEFAUtil, consultez l’article de blog Technet, «[comment obtenir SEFAutil en cours d’exécution ?](https://go.microsoft.com/fwlink/?LinkId=278940)».</span><span class="sxs-lookup"><span data-stu-id="49de8-108">For more details about running SEFAUtil, see the Technet blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="49de8-109">Pour déployer SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="49de8-109">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="49de8-110">Ouvrez une session sur l’ordinateur où est installé Skype pour Business Server Management Shell en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires, comme décrit dans **Déléguer les autorisations de configuration**.</span><span class="sxs-lookup"><span data-stu-id="49de8-110">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="49de8-111">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="49de8-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="49de8-112">L’outil SEFAUtil ne peut être exécuté que sur un ordinateur qui fait partie d’un pool d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="49de8-112">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="49de8-113">Si nécessaire, définissez un pool d’applications de confiance pour le pool de Front-End où vous envisagez d’exécuter SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="49de8-113">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="49de8-114">Dans la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="49de8-114">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. <span data-ttu-id="49de8-p102">Définissez l’outil SEFAUtil en tant qu’application approuvée. Sur la ligne de commande, exécutez :</span><span class="sxs-lookup"><span data-stu-id="49de8-p102">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="49de8-117">Vous pouvez utiliser un autre port si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="49de8-117">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="49de8-p103">Activez la topologie avec vos modifications. Sur la ligne de commande, exécutez :</span><span class="sxs-lookup"><span data-stu-id="49de8-p103">Enable the topology with your changes. At the command line, run:</span></span>
    
  ```
  Enable-CsTopology
  ```

6. <span data-ttu-id="49de8-120">Si vous ne l’avez pas déjà, téléchargez le Skype pour la version de serveur d’entreprise de l’outil SEFAUtil à partir de [cet emplacement](https://www.microsoft.com/en-us/download/details.aspx?id=52631)et les installer sur le pool d’applications d’un niveau de confiance que vous avez créé à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="49de8-120">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="49de8-121">Vérifiez que l’outil SEFAUtil s’exécute correctement ainsi :</span><span class="sxs-lookup"><span data-stu-id="49de8-121">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="49de8-122">a.</span><span class="sxs-lookup"><span data-stu-id="49de8-122">a.</span></span> <span data-ttu-id="49de8-123">Exécutez l’outil à partir de l’invite de commande Windows avec des droits d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="49de8-123">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="49de8-124">b.</span><span class="sxs-lookup"><span data-stu-id="49de8-124">b.</span></span> <span data-ttu-id="49de8-125">Affichez les paramètres de transfert d’appel d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="49de8-125">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="49de8-126">Sur la ligne de commande, exécutez :</span><span class="sxs-lookup"><span data-stu-id="49de8-126">At the command line, run:</span></span>
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

<span data-ttu-id="49de8-127">Les paramètres de transfert d’appel de l’utilisateur s’afficheront.</span><span class="sxs-lookup"><span data-stu-id="49de8-127">The call forwarding settings for the user will be displayed.</span></span>
    

