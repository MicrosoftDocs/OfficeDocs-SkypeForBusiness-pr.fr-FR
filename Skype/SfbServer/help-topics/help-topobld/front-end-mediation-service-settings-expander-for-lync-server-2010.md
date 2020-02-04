---
title: Développeur des paramètres du service de médiation frontal pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Dans cette boîte de dialogue, vous pouvez modifier les propriétés des paramètres de la passerelle RTC du serveur de médiation. Vous définissez les paramètres suivants :'
ms.openlocfilehash: bd24c24d14e24ed7e4ce53bc30d01b2e955be6cf
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697279"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="2bbc7-104">Développeur des paramètres du service de médiation frontal pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2bbc7-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="2bbc7-105">Dans cette boîte de dialogue, vous pouvez modifier les propriétés des paramètres de la **passerelle RTC du serveur de médiation** .</span><span class="sxs-lookup"><span data-stu-id="2bbc7-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="2bbc7-106">Vous définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="2bbc7-106">You define the following settings:</span></span>
  
- <span data-ttu-id="2bbc7-107">Sélectionnez le **serveur de médiation en option activé** si vous voulez Collocate le serveur de médiation avec ce serveur frontal ou les listes frontales.</span><span class="sxs-lookup"><span data-stu-id="2bbc7-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="2bbc7-108">**Ports d’écoute**: définissez les ports que le serveur de médiation va écouter.</span><span class="sxs-lookup"><span data-stu-id="2bbc7-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="2bbc7-109">Vous pouvez définir un port pour **TLS ou TLS** (Transport Layer Security), ou **TCP**ou protocole de contrôle de transport.</span><span class="sxs-lookup"><span data-stu-id="2bbc7-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="2bbc7-110">Pour que l’entrée de port du protocole TCP soit disponible, vous devez activer la case à cocher **activer le port TCP**.</span><span class="sxs-lookup"><span data-stu-id="2bbc7-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="2bbc7-111">Reportez-vous à la documentation et aux paramètres de configuration de votre passerelle RTC (réseau téléphonique commuté) pour déterminer si vous devez activer et définir des valeurs de port TLS, TCP ou les deux.</span><span class="sxs-lookup"><span data-stu-id="2bbc7-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="2bbc7-112">TLS est un protocole plus sécurisé, qui utilise des certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="2bbc7-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="2bbc7-113">Les passerelles RTC ne prennent pas en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="2bbc7-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="2bbc7-114">Une liste répertorie les **jonctions** (jonctions SIP [Session Initiation Protocol]), la **passerelle** (passerelle RTC ou système IP-PBX) et le **site** (site configuré pour la jonction et la passerelle).</span><span class="sxs-lookup"><span data-stu-id="2bbc7-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="2bbc7-p105">Sélectionnez une jonction, une passerelle et un site et cliquez sur **Utiliser par défaut** pour définir la sélection comme valeur par défaut pour ce service de médiation. Sélectionnez la valeur par défaut actuelle, puis cliquez sur **Annuler par défaut** pour supprimer la sélection comme valeur par défaut actuelle. Sélectionnez ensuite une nouvelle valeur par défaut et cliquez sur **Utiliser par défaut**.</span><span class="sxs-lookup"><span data-stu-id="2bbc7-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="2bbc7-118">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2bbc7-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="2bbc7-119">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2bbc7-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="2bbc7-120">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="2bbc7-120">**Help** Displays this help screen.</span></span>
  

