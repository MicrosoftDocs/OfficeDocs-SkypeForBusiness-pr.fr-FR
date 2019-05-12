---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contient les cookies de synchronisation Lightweight Directory Access Protocol (LDAP).
ms.openlocfilehash: d990d02e73be9a4d6178037a314e36add448ad40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929944"
---
# <a name="tbladcookie"></a><span data-ttu-id="a3c20-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="a3c20-103">tblADCookie</span></span>
 
<span data-ttu-id="a3c20-104">tblADCookie contient les cookies de synchronisation Lightweight Directory Access Protocol (LDAP).</span><span class="sxs-lookup"><span data-stu-id="a3c20-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="a3c20-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="a3c20-105">**Columns**</span></span>

|<span data-ttu-id="a3c20-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a3c20-106">**Column**</span></span>|<span data-ttu-id="a3c20-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="a3c20-107">**Type**</span></span>|<span data-ttu-id="a3c20-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="a3c20-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a3c20-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a3c20-109">prinGuid</span></span>  <br/> |<span data-ttu-id="a3c20-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="a3c20-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="a3c20-111">GUID principal du domaine en cours d’analyse.</span><span class="sxs-lookup"><span data-stu-id="a3c20-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="a3c20-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="a3c20-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="a3c20-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="a3c20-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="a3c20-114">Nom de domaine complet (FQDN) du contrôleur de domaine en cours utilisé pour la synchronisation des Services de domaine Active Directory. A la valeur d’information.</span><span class="sxs-lookup"><span data-stu-id="a3c20-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="a3c20-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="a3c20-115">adcContent</span></span>  <br/> |<span data-ttu-id="a3c20-116">image (binaire)</span><span class="sxs-lookup"><span data-stu-id="a3c20-116">image (binary)</span></span>  <br/> |<span data-ttu-id="a3c20-117">Cookie de synchronisation d’annuaires actif.</span><span class="sxs-lookup"><span data-stu-id="a3c20-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="a3c20-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="a3c20-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="a3c20-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="a3c20-119">datetime</span></span>  <br/> |<span data-ttu-id="a3c20-120">Horodatage avec l’heure de mise à jour de ligne.</span><span class="sxs-lookup"><span data-stu-id="a3c20-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="a3c20-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="a3c20-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="a3c20-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="a3c20-122">datetime</span></span>  <br/> |<span data-ttu-id="a3c20-123">Temps jusqu'à ce que la ligne est verrouillée contre les modifications.</span><span class="sxs-lookup"><span data-stu-id="a3c20-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="a3c20-124">Il fait partie d’un mécanisme de verrouillage logiciel qui garantit que seuls des services de conversation fait la synchronisation Active Directory à la fois.</span><span class="sxs-lookup"><span data-stu-id="a3c20-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="a3c20-125">**Clés**</span><span class="sxs-lookup"><span data-stu-id="a3c20-125">**Keys**</span></span>

|<span data-ttu-id="a3c20-126">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="a3c20-126">**Column(s)**</span></span>|<span data-ttu-id="a3c20-127">**Description**</span><span class="sxs-lookup"><span data-stu-id="a3c20-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3c20-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a3c20-128">prinGuid</span></span>  <br/> |<span data-ttu-id="a3c20-129">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="a3c20-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a3c20-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a3c20-130">prinGuid</span></span>  <br/> |<span data-ttu-id="a3c20-131">Clé étrangère avec recherche dans la table Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="a3c20-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

