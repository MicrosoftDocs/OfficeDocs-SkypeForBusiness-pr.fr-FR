---
title: Expanseur des paramètres généraux d’Application externe
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Pour modifier les propriétés d’un serveur d’applications approuvées qui a déjà été défini, suivez ces instructions.
ms.openlocfilehash: 11851554f9bcea39b2ae832aa69dd626989ccf8c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371408"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="097ab-103">Expanseur des paramètres généraux d’Application externe</span><span class="sxs-lookup"><span data-stu-id="097ab-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="097ab-104">Pour modifier les propriétés d’un serveur d’applications approuvées qui a déjà été défini, suivez ces instructions.</span><span class="sxs-lookup"><span data-stu-id="097ab-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="097ab-105">Il existe deux sections que vous pouvez modifier :</span><span class="sxs-lookup"><span data-stu-id="097ab-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="097ab-106">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="097ab-106">General settings</span></span>
> 
> <span data-ttu-id="097ab-107">Paramètres du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="097ab-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="097ab-108">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="097ab-108">General Settings</span></span>

<span data-ttu-id="097ab-109">Vous pouvez modifier le nom de domaine complet (FQDN) actuel pour le pool de serveurs d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="097ab-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="097ab-110">Modifiez le nom du pool de nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="097ab-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="097ab-111">Les enregistrements d’hôte (A) de nom de domaine DNS (Domain Name System) doivent exister pour que la nouvelle entrée avant de clients ou serveurs peuvent se connecter par le nouveau nom du pool.</span><span class="sxs-lookup"><span data-stu-id="097ab-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="097ab-112">Si vous avez besoin pour que la réplication des données de configuration pour ce pool, sélectionnez **Activer la réplication des données de configuration pour ce pool** .</span><span class="sxs-lookup"><span data-stu-id="097ab-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="097ab-113">Désactivez la case à cocher si vous ne souhaitez pas répliquer les données de configuration.</span><span class="sxs-lookup"><span data-stu-id="097ab-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="097ab-114">Paramètres du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="097ab-114">Next Hop Settings</span></span>

<span data-ttu-id="097ab-115">Vous pouvez spécifier le serveur du tronçon suivant du pool serveur d’applications approuvées en sélectionnant le pool frontal Enterprise Edition ou Standard Edition serveur frontal dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="097ab-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="097ab-116">Un directeur ou un directeur pool n’est pas une sélection valide pour une application approuvée tronçon suivant du serveur et n’apparaît pas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="097ab-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="097ab-117">Cliquez sur **OK** pour accepter et enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="097ab-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="097ab-118">Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.</span><span class="sxs-lookup"><span data-stu-id="097ab-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

