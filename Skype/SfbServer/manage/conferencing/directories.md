---
title: Création des annuaires de conférences dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Résumé : Apprenez à créer des répertoires de conférence dans Skype pour Business Server 2015.'
ms.openlocfilehash: aa261dbe92507fad2721f57d743be57bea89de2a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-conference-directories-in-skype-for-business-server-2015"></a><span data-ttu-id="378c4-103">Création des annuaires de conférences dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="378c4-103">Create conference directories in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="378c4-104">**Résumé :** Apprenez à créer des répertoires de conférence dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="378c4-104">**Summary:** Learn how to create conference directories in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="378c4-105">Les répertoires de conférence gèrent un mappage entre l’ID alphanumérique par un participant de participer à une conférence lors de l’utilisation de Skype pour les entreprises et l’ID de conférence numérique uniquement par un participant de la conférence à distance pour joindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="378c4-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="378c4-106">Création d’un annuaire de conférences</span><span class="sxs-lookup"><span data-stu-id="378c4-106">Create a conference directory</span></span>

<span data-ttu-id="378c4-107">La création de plusieurs annuaires des conférences permet de s’assurer que les ID de conférences restent courts jusqu’à ce qu’une quantité importante de conférences ait été créée.</span><span class="sxs-lookup"><span data-stu-id="378c4-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="378c4-p101">Dans une organisation avec un nombre type de conférences par utilisateur, nous recommandons de créer un annuaire de conférences pour chaque tranche de 999 utilisateurs. Le respect de cette consigne permet, en général, de limiter la longueur des ID de conférence. Toutefois, dès que le nombre d’annuaires de conférences (pour les pools) dépasse 9, la longueur de l’ID de conférence augmente pour prendre en charge d’autres conférences.</span><span class="sxs-lookup"><span data-stu-id="378c4-p101">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline, the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="378c4-111">Le format d’un ID de conférence est le suivant :</span><span class="sxs-lookup"><span data-stu-id="378c4-111">The format of a conference ID is as follows:</span></span> 
  
```
<housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

```

<span data-ttu-id="378c4-p102">Pour créer un annuaire de conférences, utilisez l’applet de commande **New-CsConferenceDirectory**. Par exemple, la commande ci-dessous permet de créer un annuaire de conférence avec l’identité 42, hébergé sur le pool atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="378c4-p102">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet. For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

```

<span data-ttu-id="378c4-114">Pour plus d’informations, consultez [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="378c4-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  

