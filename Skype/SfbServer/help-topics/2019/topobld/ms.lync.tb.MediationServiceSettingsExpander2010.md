---
title: Expanseur des paramètres du service de médiation pour Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Vous modifiez les propriétés du service de médiation en définissant les propriétés suivantes :'
ms.openlocfilehash: d8529a97459de70270fbe709d06c92e5a1b37af3
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="fbd95-103">Expanseur des paramètres du service de médiation pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fbd95-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="fbd95-104">Vous modifiez les propriétés du service de médiation en définissant les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="fbd95-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="fbd95-p101">**Ports d’écoute** : définissez le port **TLS** écouté par le service de médiation. Par défaut, la valeur du port TCP est le port 5067 sur TLS</span><span class="sxs-lookup"><span data-stu-id="fbd95-p101">**Listening ports**: Define the **TLS** port that the Mediation service will listen on. By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="fbd95-p102">Vous avez la possibilité de définir la valeur du port TCP****. Par défaut, la valeur du port TCP est le port 5068.</span><span class="sxs-lookup"><span data-stu-id="fbd95-p102">Optionally, you define a **TCP** port value. By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fbd95-p103">Le paramètre de la valeur du port TCP est activé en sélectionnant **Activer le port TCP**. Pour plus d’informations sur les exigences des paramètres du port pour la communication avec le service de médiation, vous devez vous reportez à la documentation de votre passerelle de réseau téléphonique commuté (RTC) ou de votre système IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="fbd95-p103">The TCP port value setting is enabled by selecting **Enable TCP port**. You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="fbd95-111">Vous **activez le port TCP** pour définir la valeur du port des communications TCP à partir de votre passerelle RTC ou de votre système IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="fbd95-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="fbd95-112">Une liste répertorie les **jonctions** (jonctions SIP [Session Initiation Protocol]), la **passerelle** (passerelle RTC ou système IP-PBX) et le **site** (site configuré pour la jonction et la passerelle).</span><span class="sxs-lookup"><span data-stu-id="fbd95-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="fbd95-p104">Sélectionnez une jonction, une passerelle et un site et cliquez sur **Utiliser par défaut** pour définir la sélection comme valeur par défaut pour ce service de médiation. Sélectionnez la valeur par défaut actuelle, puis cliquez sur **Annuler par défaut** pour supprimer la sélection comme valeur par défaut actuelle. Sélectionnez ensuite une nouvelle valeur par défaut et cliquez sur **Utiliser par défaut**.</span><span class="sxs-lookup"><span data-stu-id="fbd95-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
 <span data-ttu-id="fbd95-116">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fbd95-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="fbd95-117">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fbd95-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="fbd95-118">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="fbd95-118">**Help** Displays this help screen.</span></span>
  

