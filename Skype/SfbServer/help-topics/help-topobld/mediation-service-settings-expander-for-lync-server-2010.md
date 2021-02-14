---
title: Expanseur des paramètres du service de médiation pour Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Vous modifiez les propriétés du service de médiation en définissant les propriétés suivantes :'
ms.openlocfilehash: ddc6ab56f848179800b6398b7a638cdb7a061a9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806684"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="9ba07-103">Expandeur des paramètres du service de médiation pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9ba07-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="9ba07-104">Vous modifiez les propriétés du service de médiation en définissant les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ba07-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="9ba07-p101">**Ports d’écoute** : définissez le port **TLS** sur lequel le service de médiation écoutera. Par défaut, la valeur du port est TCP 5067 sur TLS</span><span class="sxs-lookup"><span data-stu-id="9ba07-p101">**Listening ports**: Define the **TLS** port that the Mediation service will listen on. By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="9ba07-p102">Éventuellement, vous définissez la valeur du port **TCP**. Par défaut, la valeur du port TCP est 5068.</span><span class="sxs-lookup"><span data-stu-id="9ba07-p102">Optionally, you define a **TCP** port value. By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9ba07-p103">Le paramètre de la valeur du port TCP est activé en sélectionnant **Activer le port TCP**. Vous devriez consulter la documentation de votre passerelle de réseau téléphonique commuté (PSTN) ou de votre système IP-PBX pour obtenir la configuration requise des paramètres du port pour communiquer avec le service de médiation.</span><span class="sxs-lookup"><span data-stu-id="9ba07-p103">The TCP port value setting is enabled by selecting **Enable TCP port**. You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="9ba07-111">Vous pouvez **activer le port TCP** pour définir la valeur du port des communications TCP à partir de votre passerelle PSTN ou de votre système IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="9ba07-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="9ba07-112">Une liste d’éléments existants et actuellement associés en matière de **Jonction** (c’est-à-dire, jonctions SIP (Session Initiation Protocol)), de **Passerelle** (passerelle PSTN ou système IP-PBX) et de **Site** (site configuré pour la jonction et la passerelle).</span><span class="sxs-lookup"><span data-stu-id="9ba07-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="9ba07-p104">Sélectionnez une jonction, une passerelle et un site, puis cliquez sur **Utiliser par défaut** pour définir la sélection en tant que valeur par défaut pour ce service de médiation. Sélectionnez la valeur par défaut actuelle, puis cliquez sur **Annuler Par défaut** pour supprimer la sélection en tant que valeur par défaut actuelle. Sélectionnez ensuite une nouvelle valeur par défaut, puis cliquez sur **Utiliser par défaut**.</span><span class="sxs-lookup"><span data-stu-id="9ba07-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="9ba07-116">**OK** permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9ba07-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="9ba07-117">**Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9ba07-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="9ba07-118">**Aide** permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="9ba07-118">**Help** Displays this help screen.</span></span>
  

