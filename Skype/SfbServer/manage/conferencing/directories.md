---
title: Créer des annuaires des conférences dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Résumé : Découvrez comment créer des annuaires des conférences dans Skype Entreprise Server.'
ms.openlocfilehash: 6a7b8d110f06b089f166fc6ff2eb35ae35632370
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828134"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="bd61a-103">Créer des annuaires des conférences dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bd61a-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="bd61a-104">**Résumé :** Découvrez comment créer des annuaires des conférences dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="bd61a-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="bd61a-105">Les annuaires des conférences conservent un mappage entre l’ID de réunion alphanumérique qu’un participant utilise pour participer à une conférence lors de l’utilisation de Skype Entreprise et l’ID de conférence numérique uniquement qu’un participant à une conférence rendez-vous utilise pour participer à la conférence.</span><span class="sxs-lookup"><span data-stu-id="bd61a-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="bd61a-106">Créer un annuaire des conférences</span><span class="sxs-lookup"><span data-stu-id="bd61a-106">Create a conference directory</span></span>

<span data-ttu-id="bd61a-107">La création de plusieurs annuaires des conférences garantit que les ID de conférence resteront courts jusqu’à ce qu’une quantité importante de conférences soit créée.</span><span class="sxs-lookup"><span data-stu-id="bd61a-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="bd61a-108">Dans une organisation avec un nombre typique de conférences par utilisateur, nous vous recommandons de créer un annuaire de conférences pour 999 utilisateurs dans le pool.</span><span class="sxs-lookup"><span data-stu-id="bd61a-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="bd61a-109">À l’aide de cette recommandation, les ID de conférence peuvent généralement rester petits.</span><span class="sxs-lookup"><span data-stu-id="bd61a-109">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="bd61a-110">Toutefois, une fois que le nombre d’annuaires des conférences (dans les pools) dépasse 9, la longueur de l’ID de conférence augmente pour prendre en charge des conférences supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="bd61a-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="bd61a-111">Le format d’un ID de conférence est le suivant :</span><span class="sxs-lookup"><span data-stu-id="bd61a-111">The format of a conference ID is as follows:</span></span> 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="bd61a-112">Pour créer un annuaire des conférences, utilisez l’cmdlet **New-CsConferenceDirectory.**</span><span class="sxs-lookup"><span data-stu-id="bd61a-112">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet.</span></span> <span data-ttu-id="bd61a-113">Par exemple, la commande suivante crée un annuaire de conférences avec l’identité 42, hébergé sur le pool atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="bd61a-113">For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="bd61a-114">Pour plus d’informations, [voir New-CsConferenceDirectory.](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="bd61a-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  

