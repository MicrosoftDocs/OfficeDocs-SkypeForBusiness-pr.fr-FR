---
title: Expanseur des paramètres du service de médiation frontal pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Vous modifiez les propriétés des paramètres de Passerelle PSTN du serveur de médiation dans cette boîte de dialogue. Vous définissez les paramètres suivants :'
ms.openlocfilehash: 37baf89b6100528c1485f939f69e20c697803123
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217725"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="3dd17-104">Expanseur des paramètres du service de médiation frontal pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3dd17-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="3dd17-105">Vous modifiez les propriétés des paramètres de **Passerelle PSTN du serveur de médiation** dans cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3dd17-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="3dd17-106">Vous définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="3dd17-106">You define the following settings:</span></span>
  
- <span data-ttu-id="3dd17-107">Sélectionnez le **serveur de médiation colocalisé activé** si vous souhaitez colocaliser le serveur de médiation avec ce serveur frontal ou des pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="3dd17-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="3dd17-108">**Ports d’écoute**: définissez les ports que le serveur de médiation doit écouter.</span><span class="sxs-lookup"><span data-stu-id="3dd17-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="3dd17-109">Vous pouvez définir un port pour le protocole **TLS** (Transport Layer Security) ou **TCP** (Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="3dd17-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="3dd17-110">Pour que l’entrée du port TCP soit disponible, vous devez activer la case à cocher **Activer le port TCP**.</span><span class="sxs-lookup"><span data-stu-id="3dd17-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="3dd17-111">Consultez la documentation et les paramètres de configuration de votre passerelle de réseau téléphonique commuté (PSTN) pour déterminer si vous devez activer et définir les valeurs du port TLS, TCP ou les deux.</span><span class="sxs-lookup"><span data-stu-id="3dd17-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="3dd17-112">TLS est un protocole plus sécurisé, qui utilise des certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="3dd17-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="3dd17-113">Certaines passerelles PSTN ne prennent pas en charge TLS.</span><span class="sxs-lookup"><span data-stu-id="3dd17-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="3dd17-114">Une liste d’éléments existants et actuellement associés en matière de **Jonction** (c’est-à-dire, jonctions SIP (Session Initiation Protocol)), de **Passerelle** (passerelle PSTN ou système IP-PBX) et de **Site** (site configuré pour la jonction et la passerelle).</span><span class="sxs-lookup"><span data-stu-id="3dd17-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="3dd17-p105">Sélectionnez une jonction, une passerelle et un site, puis cliquez sur **Utiliser par défaut** pour définir la sélection en tant que valeur par défaut pour ce service de médiation. Sélectionnez la valeur par défaut actuelle, puis cliquez sur **Annuler Par défaut** pour supprimer la sélection en tant que valeur par défaut actuelle. Sélectionnez ensuite une nouvelle valeur par défaut, puis cliquez sur **Utiliser par défaut**.</span><span class="sxs-lookup"><span data-stu-id="3dd17-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="3dd17-118">**OK** permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3dd17-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="3dd17-119">**Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3dd17-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="3dd17-120">**Aide** permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="3dd17-120">**Help** Displays this help screen.</span></span>
  

