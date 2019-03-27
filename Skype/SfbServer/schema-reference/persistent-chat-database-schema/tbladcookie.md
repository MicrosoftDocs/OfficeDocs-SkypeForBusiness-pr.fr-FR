---
title: tblADCookie
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contient les cookies de synchronisation Lightweight Directory Access Protocol (LDAP).
ms.openlocfilehash: 3e7eeeeae6623bbbb308f4e05c4ab8a4b9a7be50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890979"
---
# <a name="tbladcookie"></a><span data-ttu-id="e6f03-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="e6f03-103">tblADCookie</span></span>
 
<span data-ttu-id="e6f03-104">tblADCookie contient les cookies de synchronisation Lightweight Directory Access Protocol (LDAP).</span><span class="sxs-lookup"><span data-stu-id="e6f03-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="e6f03-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="e6f03-105">**Columns**</span></span>

|<span data-ttu-id="e6f03-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e6f03-106">**Column**</span></span>|<span data-ttu-id="e6f03-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="e6f03-107">**Type**</span></span>|<span data-ttu-id="e6f03-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="e6f03-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6f03-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e6f03-109">prinGuid</span></span>  <br/> |<span data-ttu-id="e6f03-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="e6f03-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="e6f03-111">GUID principal du domaine en cours d’analyse.</span><span class="sxs-lookup"><span data-stu-id="e6f03-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="e6f03-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="e6f03-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="e6f03-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="e6f03-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="e6f03-114">Nom de domaine complet (FQDN) du contrôleur de domaine en cours utilisé pour la synchronisation des Services de domaine Active Directory. A la valeur d’information.</span><span class="sxs-lookup"><span data-stu-id="e6f03-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="e6f03-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="e6f03-115">adcContent</span></span>  <br/> |<span data-ttu-id="e6f03-116">image (binaire)</span><span class="sxs-lookup"><span data-stu-id="e6f03-116">image (binary)</span></span>  <br/> |<span data-ttu-id="e6f03-117">Cookie de synchronisation d’annuaires actif.</span><span class="sxs-lookup"><span data-stu-id="e6f03-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="e6f03-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="e6f03-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="e6f03-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e6f03-119">datetime</span></span>  <br/> |<span data-ttu-id="e6f03-120">Horodatage avec l’heure de mise à jour de ligne.</span><span class="sxs-lookup"><span data-stu-id="e6f03-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="e6f03-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="e6f03-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="e6f03-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e6f03-122">datetime</span></span>  <br/> |<span data-ttu-id="e6f03-123">Temps jusqu'à ce que la ligne est verrouillée contre les modifications.</span><span class="sxs-lookup"><span data-stu-id="e6f03-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="e6f03-124">Il fait partie d’un mécanisme de verrouillage logiciel qui garantit que seuls des services de conversation fait la synchronisation Active Directory à la fois.</span><span class="sxs-lookup"><span data-stu-id="e6f03-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="e6f03-125">**Clés**</span><span class="sxs-lookup"><span data-stu-id="e6f03-125">**Keys**</span></span>

|<span data-ttu-id="e6f03-126">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="e6f03-126">**Column(s)**</span></span>|<span data-ttu-id="e6f03-127">**Description**</span><span class="sxs-lookup"><span data-stu-id="e6f03-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6f03-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e6f03-128">prinGuid</span></span>  <br/> |<span data-ttu-id="e6f03-129">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="e6f03-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e6f03-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e6f03-130">prinGuid</span></span>  <br/> |<span data-ttu-id="e6f03-131">Clé étrangère avec recherche dans la table Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="e6f03-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

