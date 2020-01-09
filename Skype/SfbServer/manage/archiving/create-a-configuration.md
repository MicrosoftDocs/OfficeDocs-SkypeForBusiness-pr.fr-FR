---
title: Créer une configuration d’archivage dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Résumé : Découvrez comment créer une configuration d’archivage pour Skype entreprise Server.'
ms.openlocfilehash: bd2a139e7321542e3b13259ebc2ec1e4ba731caf
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992741"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="49a93-103">Créer une configuration d’archivage dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="49a93-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="49a93-104">**Résumé :** Découvrez comment créer une configuration d’archivage pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="49a93-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="49a93-105">Configurer les options d’archivage à l’aide du panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="49a93-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="49a93-106">Pour configurer des options d’archivage pour un site ou un pool :</span><span class="sxs-lookup"><span data-stu-id="49a93-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="49a93-107">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="49a93-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="49a93-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="49a93-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="49a93-109">Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="49a93-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="49a93-110">Dans la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="49a93-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="49a93-111">Pour créer une configuration d’archivage de site, cliquez sur **Configuration du site** et, dans **Sélectionner un site**, indiquez le site à configurer pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="49a93-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="49a93-112">Pour créer une configuration d’archivage de pool, cliquez sur **Configuration du pool** et, dans **Sélectionner un pool**, indiquez le pool à configurer pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="49a93-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="49a93-113">Dans **Nouveau paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="49a93-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="49a93-114">Afin d’activer l’archivage seulement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.</span><span class="sxs-lookup"><span data-stu-id="49a93-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="49a93-115">Afin d’activer l’archivage aussi bien pour les sessions de messagerie instantanée que les conférences web, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence web**.</span><span class="sxs-lookup"><span data-stu-id="49a93-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="49a93-116">Afin de désactiver l’archivage pour cette configuration, cliquez sur **Désactiver l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="49a93-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="49a93-117">Aussi, dans **Créer un paramètre d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="49a93-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="49a93-118">Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="49a93-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="49a93-119">Pour utiliser Microsoft Exchange Server pour stocker des données d’archivage, activez la case à cocher **intégration Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="49a93-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="49a93-120">Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="49a93-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="49a93-121">Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="49a93-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="49a93-122">Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.</span><span class="sxs-lookup"><span data-stu-id="49a93-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="49a93-123">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="49a93-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="49a93-124">Configurer les options d’archivage à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49a93-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="49a93-125">Vous pouvez aussi configurer des options d’archivage pour un site ou un pool spécifique en utilisant l’applet de commande **New-CsArchivingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="49a93-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="49a93-126">La commande suivante crée une collection de paramètres de configuration d’archivage pour le site Redmond :</span><span class="sxs-lookup"><span data-stu-id="49a93-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="49a93-127">Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="49a93-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="49a93-p101">Pour créer des paramètres qui utilisent des valeurs de propriété différentes, il suffit d’inclure le paramètre et la valeur de paramètre appropriés. L’exemple suivant crée une collection de paramètres de configuration d’archivage qui, par défaut, autorise uniquement l’archivage des sessions de messagerie instantanée :</span><span class="sxs-lookup"><span data-stu-id="49a93-p101">To create settings that use different property values, simply include the appropriate parameter and parameter value. The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="49a93-p102">Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres pour archiver les sessions de messagerie instantanée et pour bloquer la messagerie du service d’archivage afin de le rendre non disponible :</span><span class="sxs-lookup"><span data-stu-id="49a93-p102">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="49a93-132">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de [nouvelle-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="49a93-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
