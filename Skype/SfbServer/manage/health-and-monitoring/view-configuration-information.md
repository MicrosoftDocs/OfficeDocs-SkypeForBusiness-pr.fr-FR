---
title: Affichage des informations de configuration de l’enregistrement des détails des appels dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Résumé : Apprenez à utiliser l’enregistrement de détail appels (CDR) dans Skype pour Business Server 2015.'
ms.openlocfilehash: 6eacc6c300cfc1faae843a1dc610b17b45ae9c88
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server-2015"></a><span data-ttu-id="f5edf-103">Affichage des informations de configuration de l’enregistrement des détails des appels dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="f5edf-103">View CDR configuration information in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f5edf-104">**Résumé :** Apprenez à utiliser d’enregistrement de détail appels (CDR) dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f5edf-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f5edf-p101">L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.</span><span class="sxs-lookup"><span data-stu-id="f5edf-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="f5edf-107">Lorsque vous installez Skype pour Business Server 2015, une seule collection globale CDR de paramètres de configuration est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="f5edf-107">When you install Skype for Business Server 2015, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="f5edf-108">Les administrateurs ont également la possibilité de créer des collections de paramètres personnalisées applicables à des sites individuels.</span><span class="sxs-lookup"><span data-stu-id="f5edf-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="f5edf-109">Vous pouvez afficher les paramètres de configuration de CD-r en cours d’utilisation dans votre organisation à l’aide de Skype pour Business Server du Panneau de configuration ou l’applet de commande [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f5edf-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f5edf-110">Pour afficher les informations de configuration de CD-r pour le panneau de configuration de Business Server à l’aide de Skype</span><span class="sxs-lookup"><span data-stu-id="f5edf-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f5edf-111">Dans Skype pour le panneau de configuration de Business Server, cliquez sur **surveillance et archivage**.</span><span class="sxs-lookup"><span data-stu-id="f5edf-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="f5edf-p103">La liste de tous vos paramètres de configuration d’enregistrement des détails des appels s’affiche sous l’onglet **Enregistrement des détails des appels** ; pour chaque collection de paramètres apparaissent la collection **Nom**, l’indication stipulant si l’enregistrement des détails des appels a été activé ou non (propriété **Enregistrement des détails des appels**) et l’indication stipulant si le vidage a été activé (propriété **Vidage de l’enregistrement des détails des appels**). Pour plus d’informations sur une collection, double-cliquez dessus ou sélectionnez la collection appropriée, cliquez sur **Modifier**, puis sur **Afficher les détails**. Notez que vous pouvez uniquement afficher des informations détaillées pour une seule collection de paramètres de configuration d’enregistrement des détails des appels à la fois.</span><span class="sxs-lookup"><span data-stu-id="f5edf-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f5edf-115">CD-r de l’affichage des informations de configuration à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5edf-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f5edf-116">Vous pouvez afficher les paramètres de configuration de CD-r à l’aide de Windows PowerShell et l’applet de commande Get-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f5edf-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="f5edf-117">Vous pouvez exécuter cette applet de commande depuis le Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5edf-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f5edf-118">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="f5edf-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f5edf-119">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="f5edf-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="f5edf-120">Pour afficher les informations de configuration d’enregistrement des détails des appels</span><span class="sxs-lookup"><span data-stu-id="f5edf-120">To view CDR configuration information</span></span>

- <span data-ttu-id="f5edf-121">Pour afficher des informations sur tous vos paramètres de configuration de CD-r, tapez la commande suivante dans la Skype pour Business Server Management Shell et puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="f5edf-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="f5edf-122">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="f5edf-122">That will return information similar to this:</span></span>
    
  ```
  Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2

  ```

<span data-ttu-id="f5edf-123">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f5edf-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

