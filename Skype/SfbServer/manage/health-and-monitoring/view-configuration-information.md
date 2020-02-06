---
title: Afficher les informations de configuration de CDR dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Résumé : Découvrez comment utiliser l’enregistrement des détails des appels (CDR) dans Skype entreprise Server.'
ms.openlocfilehash: f4a216f1c2d8892370b80eef42c19cf07c133312
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817593"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="93ff5-103">Afficher les informations de configuration de CDR dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="93ff5-103">View CDR configuration information in Skype for Business Server</span></span>
 
<span data-ttu-id="93ff5-104">**Résumé :** Découvrez comment utiliser l’enregistrement des détails des appels dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="93ff5-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="93ff5-p101">L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.</span><span class="sxs-lookup"><span data-stu-id="93ff5-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="93ff5-107">Lorsque vous installez Skype entreprise Server, une collection globale unique de paramètres de configuration de CDR est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="93ff5-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="93ff5-108">Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels.</span><span class="sxs-lookup"><span data-stu-id="93ff5-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="93ff5-109">Vous pouvez afficher les paramètres de configuration de CDR utilisés au sein de votre organisation à l’aide du panneau de configuration Skype entreprise Server ou de l’applet de commande [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="93ff5-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="93ff5-110">Pour afficher les informations de configuration de CDR en utilisant le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="93ff5-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="93ff5-111">Dans le panneau de configuration Skype entreprise Server, cliquez sur **surveillance et archivage**.</span><span class="sxs-lookup"><span data-stu-id="93ff5-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="93ff5-p103">La liste de tous vos paramètres de configuration d’enregistrement des détails des appels s’affiche sous l’onglet **Enregistrement des détails des appels** ; pour chaque collection de paramètres apparaissent la collection **Nom**, l’indication stipulant si l’enregistrement des détails des appels a été activé ou non (propriété **Enregistrement des détails des appels**) et l’indication stipulant si le vidage a été activé (propriété **Vidage de l’enregistrement des détails des appels**). Pour plus d’informations sur une collection, double-cliquez dessus ou sélectionnez la collection appropriée, cliquez sur **Modifier**, puis sur **Afficher les détails**. Notez que vous pouvez uniquement afficher des informations détaillées pour une seule collection de paramètres de configuration d’enregistrement des détails des appels à la fois.</span><span class="sxs-lookup"><span data-stu-id="93ff5-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="93ff5-115">Affichage des informations de configuration de CDR à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="93ff5-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="93ff5-116">Vous pouvez afficher les paramètres de configuration de CDR à l’aide de Windows PowerShell et de l’applet de cmdlet Get-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="93ff5-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="93ff5-117">Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93ff5-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="93ff5-118">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="93ff5-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="93ff5-119">Le processus est le même dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="93ff5-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="93ff5-120">Pour afficher les informations de configuration d’enregistrement des détails des appels</span><span class="sxs-lookup"><span data-stu-id="93ff5-120">To view CDR configuration information</span></span>

- <span data-ttu-id="93ff5-121">Pour afficher des informations sur les paramètres de configuration de votre CDR, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="93ff5-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="93ff5-122">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="93ff5-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="93ff5-123">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="93ff5-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

