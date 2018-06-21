---
title: Expanseur des paramètres du Service de Front-End médiation pour Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Vous modifiez les propriétés des paramètres de la passerelle PSTN de serveur de médiation dans cette boîte de dialogue. Vous définissez les paramètres suivants :'
ms.openlocfilehash: 7343fb4e2876ffa23fa7d37a8669f9b0c25f428b
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979770"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b6bed-104">Expanseur des paramètres du Service de Front-End médiation pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b6bed-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b6bed-105">Vous modifiez les propriétés des paramètres de la **passerelle PSTN de serveur de médiation** dans cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b6bed-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="b6bed-106">Vous définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="b6bed-106">You define the following settings:</span></span>
  
- <span data-ttu-id="b6bed-107">Sélectionnez **serveur de médiation colocalisé activé** si vous voulez colocaliser le serveur de médiation avec ce serveur frontal ou pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="b6bed-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="b6bed-108">**Ports d’écoute**: définir les ports d’écoute sur le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="b6bed-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="b6bed-109">Vous pouvez définir un port pour **TLS** ou transport layer security, ou **TCP**, ou le protocole de transport.</span><span class="sxs-lookup"><span data-stu-id="b6bed-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="b6bed-110">Pour l’entrée de port TCP soit disponible, vous devez sélectionner la case à cocher pour **le port TCP activer**.</span><span class="sxs-lookup"><span data-stu-id="b6bed-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="b6bed-111">Consultez les paramètres de configuration et de la documentation de votre passerelle de réseau téléphonique commuté pour déterminer si vous souhaitez activer et définir les valeurs de ports TLS, TCP ou les deux.</span><span class="sxs-lookup"><span data-stu-id="b6bed-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="b6bed-112">TLS est un protocole plus sécurisé, l’utilisation de certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="b6bed-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="b6bed-113">Pas toutes les passerelles PSTN prend en charge TLS.</span><span class="sxs-lookup"><span data-stu-id="b6bed-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="b6bed-114">Une liste répertorie les **jonctions** (jonctions SIP [Session Initiation Protocol]), la **passerelle** (passerelle RTC ou système IP-PBX) et le **site** (site configuré pour la jonction et la passerelle).</span><span class="sxs-lookup"><span data-stu-id="b6bed-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="b6bed-p105">Sélectionnez une jonction, une passerelle et un site et cliquez sur **Utiliser par défaut** pour définir la sélection comme valeur par défaut pour ce service de médiation. Sélectionnez la valeur par défaut actuelle, puis cliquez sur **Annuler par défaut** pour supprimer la sélection comme valeur par défaut actuelle. Sélectionnez ensuite une nouvelle valeur par défaut et cliquez sur **Utiliser par défaut**.</span><span class="sxs-lookup"><span data-stu-id="b6bed-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
 <span data-ttu-id="b6bed-118">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b6bed-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="b6bed-119">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b6bed-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="b6bed-120">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="b6bed-120">**Help** Displays this help screen.</span></span>
  

