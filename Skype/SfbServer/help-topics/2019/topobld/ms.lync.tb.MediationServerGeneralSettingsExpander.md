---
title: Expanseur des paramètres généraux du serveur de médiation
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 27a93cb0894f7791b689e4b8fcc3246ab6d9415d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979748"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="1f01b-102">Expanseur des paramètres généraux du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="1f01b-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="1f01b-103">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="1f01b-103">General settings</span></span>

<span data-ttu-id="1f01b-104">Nom de domaine complet (FQDN) du serveur de médiation pool ou du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1f01b-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="1f01b-105">Modifiez le nom de domaine complet du serveur pour changer la valeur.</span><span class="sxs-lookup"><span data-stu-id="1f01b-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="1f01b-106">Vous devez disposer d’un enregistrement d’hôte DNS (A) correspondant à la nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="1f01b-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="1f01b-107">Dans la section **Associations** , vous sélectionnez un serveur Edge ou pool de serveurs Edge à associer au pool de serveurs de médiation ou un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1f01b-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="1f01b-108">Vous sélectionnez le bord utilisées par les composants médias le serveur de médiation pour un utilisateur externe Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1f01b-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="1f01b-109">Si vous n’avez pas un serveur Edge actuellement définis et devez associer le serveur de médiation à un serveur de périphérie, cliquez sur **Nouveau** et définir le nouveau serveur de périphérie ou le pool de serveur de périphérie dans la définition de l’Assistant Nouveau Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="1f01b-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="1f01b-110">Paramètres du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="1f01b-110">Next hop settings</span></span>

<span data-ttu-id="1f01b-111">Vous spécifiez le serveur ou du pool du tronçon suivant du serveur de médiation en sélectionnant le défini pool frontal Enterprise Edition ou Standard Edition serveur frontal dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="1f01b-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="1f01b-112">Un directeur ou un directeur pool n’est pas une sélection valide pour un serveur ou du pool du tronçon suivant du serveur de médiation et n’apparaît pas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1f01b-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="1f01b-113">Cliquez sur **OK** pour accepter et enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="1f01b-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="1f01b-114">Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.</span><span class="sxs-lookup"><span data-stu-id="1f01b-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="1f01b-115">Paramètres de la passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="1f01b-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="1f01b-116">Vous définissez des passerelles PSTN qui sont associés au pool de serveurs de médiation ou un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1f01b-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="1f01b-117">Si vous avez déjà défini des passerelles, ils seront disponibles à associer au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1f01b-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="1f01b-118">Si vous activez la colocalisation du serveur de médiation, définissez la plage de ports d’écoute des serveurs du pool pour le protocole TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="1f01b-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="1f01b-119">Par défaut, il s’agit du port 5067.</span><span class="sxs-lookup"><span data-stu-id="1f01b-119">By default, this port is 5067.</span></span> <span data-ttu-id="1f01b-120">Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="1f01b-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="1f01b-121">Il s’agit d’un paramètre facultatif, et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin.</span><span class="sxs-lookup"><span data-stu-id="1f01b-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="1f01b-122">Par défaut, le port TCP est le port 5068.</span><span class="sxs-lookup"><span data-stu-id="1f01b-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="1f01b-p105">Jonctions associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1f01b-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="1f01b-125">Si vous avez plusieurs jonction associée à un serveur de médiation, vous pouvez spécifier une jonction par défaut en sélectionnant la jonction puis en cliquant sur **Utiliser par défaut**.</span><span class="sxs-lookup"><span data-stu-id="1f01b-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="1f01b-126">Pour désélectionner une passerelle par défaut, cliquez sur **Annuler par défaut**.</span><span class="sxs-lookup"><span data-stu-id="1f01b-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

