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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213157"
---
# <a name="tbladcookie"></a><span data-ttu-id="09e07-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="09e07-103">tblADCookie</span></span>
 
<span data-ttu-id="09e07-104">tblADCookie contient les cookies de synchronisation Lightweight Directory Access Protocol (LDAP).</span><span class="sxs-lookup"><span data-stu-id="09e07-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="09e07-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="09e07-105">**Columns**</span></span>

|<span data-ttu-id="09e07-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="09e07-106">**Column**</span></span>|<span data-ttu-id="09e07-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="09e07-107">**Type**</span></span>|<span data-ttu-id="09e07-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="09e07-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="09e07-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="09e07-109">prinGuid</span></span>  <br/> |<span data-ttu-id="09e07-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="09e07-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="09e07-111">GUID principal du domaine en cours d’analyse.</span><span class="sxs-lookup"><span data-stu-id="09e07-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="09e07-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="09e07-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="09e07-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="09e07-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="09e07-114">Nom de domaine complet (FQDN) du contrôleur de domaine en cours utilisé pour la synchronisation des Services de domaine Active Directory. A la valeur d’information.</span><span class="sxs-lookup"><span data-stu-id="09e07-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="09e07-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="09e07-115">adcContent</span></span>  <br/> |<span data-ttu-id="09e07-116">image (binaire)</span><span class="sxs-lookup"><span data-stu-id="09e07-116">image (binary)</span></span>  <br/> |<span data-ttu-id="09e07-117">Cookie de synchronisation d’annuaires actif.</span><span class="sxs-lookup"><span data-stu-id="09e07-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="09e07-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="09e07-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="09e07-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="09e07-119">datetime</span></span>  <br/> |<span data-ttu-id="09e07-120">Horodatage avec l’heure de mise à jour de ligne.</span><span class="sxs-lookup"><span data-stu-id="09e07-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="09e07-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="09e07-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="09e07-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="09e07-122">datetime</span></span>  <br/> |<span data-ttu-id="09e07-123">Temps jusqu'à ce que la ligne est verrouillée contre les modifications.</span><span class="sxs-lookup"><span data-stu-id="09e07-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="09e07-124">Il fait partie d’un mécanisme de verrouillage logiciel qui garantit que seuls des services de conversation fait la synchronisation Active Directory à la fois.</span><span class="sxs-lookup"><span data-stu-id="09e07-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="09e07-125">**Clés**</span><span class="sxs-lookup"><span data-stu-id="09e07-125">**Keys**</span></span>

|<span data-ttu-id="09e07-126">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="09e07-126">**Column(s)**</span></span>|<span data-ttu-id="09e07-127">**Description**</span><span class="sxs-lookup"><span data-stu-id="09e07-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="09e07-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="09e07-128">prinGuid</span></span>  <br/> |<span data-ttu-id="09e07-129">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="09e07-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="09e07-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="09e07-130">prinGuid</span></span>  <br/> |<span data-ttu-id="09e07-131">Clé étrangère avec recherche dans la table Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="09e07-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

