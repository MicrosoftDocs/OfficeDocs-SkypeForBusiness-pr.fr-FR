---
title: Agrandissement des paramètres généraux de l’Application externe
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Pour modifier les propriétés d’un serveur d’application de confiance qui a déjà été défini, suivez ces instructions.
ms.openlocfilehash: 4104b9cf22a3db36afd159c0b7d9812142112ece
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="91194-103">Agrandissement des paramètres généraux de l’Application externe</span><span class="sxs-lookup"><span data-stu-id="91194-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="91194-104">Pour modifier les propriétés d’un serveur d’application de confiance qui a déjà été défini, suivez ces instructions.</span><span class="sxs-lookup"><span data-stu-id="91194-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="91194-105">Il existe deux sections que vous pouvez modifier :</span><span class="sxs-lookup"><span data-stu-id="91194-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="91194-106">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="91194-106">General settings</span></span>
    
> <span data-ttu-id="91194-107">Paramètres du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="91194-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="91194-108">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="91194-108">General Settings</span></span>

<span data-ttu-id="91194-109">Vous pouvez modifier le nom de domaine complet (FQDN) en cours pour le pool de serveur d’application de confiance.</span><span class="sxs-lookup"><span data-stu-id="91194-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="91194-110">Modifier le nom de la grappe de nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="91194-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="91194-111">Les enregistrements de l’hôte (A) du système de nom de domaine (DNS) doivent exister pour la nouvelle entrée avant de clients ou de serveurs peuvent se connecter par le nouveau nom du pool.</span><span class="sxs-lookup"><span data-stu-id="91194-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="91194-112">Si vous avez besoin pour que la réplication des données de configuration pour ce pool, sélectionnez **Activer la réplication des données de configuration pour ce pool** .</span><span class="sxs-lookup"><span data-stu-id="91194-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="91194-113">Désactivez la case à cocher si vous ne souhaitez pas répliquer les données de configuration.</span><span class="sxs-lookup"><span data-stu-id="91194-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="91194-114">Les paramètres de saut suivant</span><span class="sxs-lookup"><span data-stu-id="91194-114">Next Hop Settings</span></span>

<span data-ttu-id="91194-115">Vous pouvez spécifier le serveur du tronçon suivant la confiance server pool d’applications en sélectionnant le pool frontal de Enterprise Edition ou Standard Edition serveur frontal dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="91194-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="91194-116">Un directeur ou un directeur pool n’est pas une sélection valide pour un saut suivant du serveur application sécurisée et n’apparaîtra pas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="91194-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  
## 

<span data-ttu-id="91194-117">Cliquez sur **OK** pour accepter et enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="91194-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="91194-118">Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.</span><span class="sxs-lookup"><span data-stu-id="91194-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

