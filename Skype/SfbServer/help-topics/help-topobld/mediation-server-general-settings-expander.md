---
title: Expanseur des paramètres généraux du serveur de médiation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: bd3047832b23604f87a1e298a42798b13bb6822a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215165"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="afffd-102">Expanseur des paramètres généraux du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="afffd-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="afffd-103">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="afffd-103">General settings</span></span>

<span data-ttu-id="afffd-p101">Nom de domaine complet (FQDN) du serveur de médiation ou du pool de serveurs de médiation. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement DNS A (hôte) qui corresponde à la nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="afffd-p101">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="afffd-107">Dans la section **Associations**, sélectionnez un serveur Edge ou un pool de serveurs Edge à associer au serveur de médiation ou au pool de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="afffd-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="afffd-108">Vous sélectionnez le serveur Edge que les composants multimédias du serveur de médiation utiliseront pour la voix entreprise de l’utilisateur externe.</span><span class="sxs-lookup"><span data-stu-id="afffd-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="afffd-109">Si vous ne disposez pas de serveur Edge actuellement défini et que vous avez besoin d’associer le serveur de médiation à un serveur Edge, cliquez sur **Nouveau** et définissez le nouveau serveur Edge ou le pool de serveurs Edge dans l’Assistant Définir le nouveau pool Edge.</span><span class="sxs-lookup"><span data-stu-id="afffd-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="afffd-110">Paramètres du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="afffd-110">Next hop settings</span></span>

<span data-ttu-id="afffd-111">Vous spécifiez le pool de serveurs de médiation ou le tronçon suivant du serveur de médiation en sélectionnant le pool frontal Enterprise Edition défini ou le serveur frontal Standard Edition dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="afffd-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="afffd-112">Un directeur ou un pool directeur n’est pas une sélection valide pour le pool de serveurs de médiation ou le tronçon suivant du serveur de médiation, et ils n’apparaîtront pas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="afffd-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="afffd-113">Cliquez sur **OK** pour accepter et enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="afffd-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="afffd-114">Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.</span><span class="sxs-lookup"><span data-stu-id="afffd-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="afffd-115">Paramètres de la passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="afffd-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="afffd-p104">Vous définissez les passerelles PSTN qui sont associées au serveur ou au pool de serveurs de médiation. Si vous avez déjà défini des passerelles, ces dernières pourront être associées au serveur de médiation. Si vous activez la fonctionnalité de colocalisation du serveur de médiation, définissez la plage de ports d’écoute des serveurs du pool pour le protocole TLS (Transport Layer Security). Par défaut, ce port est 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP (Transmission Control Protocol) pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est 5068.</span><span class="sxs-lookup"><span data-stu-id="afffd-p104">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="afffd-p105">Jonctions associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="afffd-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="afffd-p106">Si plusieurs jonctions sont associées à un serveur de médiation, vous pouvez spécifier une jonction par défaut en sélectionnant la jonction et en cliquant sur**Utiliser par défaut**. Pour désélectionner une passerelle par défaut, cliquez sur **Annuler Par défaut**.</span><span class="sxs-lookup"><span data-stu-id="afffd-p106">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

