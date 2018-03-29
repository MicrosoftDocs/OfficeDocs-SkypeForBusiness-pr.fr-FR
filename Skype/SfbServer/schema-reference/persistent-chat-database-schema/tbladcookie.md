---
title: tblADCookie
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contient les cookies en cours de la synchronisation de Lightweight Directory Access Protocol (LDAP).
ms.openlocfilehash: bc2c0657caa66a0420bc493bf4b688a2a081db36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tbladcookie"></a><span data-ttu-id="e3902-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="e3902-103">tblADCookie</span></span>
 
<span data-ttu-id="e3902-104">tblADCookie contient les cookies en cours de la synchronisation de Lightweight Directory Access Protocol (LDAP).</span><span class="sxs-lookup"><span data-stu-id="e3902-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="e3902-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="e3902-105">**Columns**</span></span>

|<span data-ttu-id="e3902-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e3902-106">**Column**</span></span>|<span data-ttu-id="e3902-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="e3902-107">**Type**</span></span>|<span data-ttu-id="e3902-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="e3902-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3902-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e3902-109">prinGuid</span></span>  <br/> |<span data-ttu-id="e3902-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="e3902-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="e3902-111">GUID principal du domaine en cours d’analyse.</span><span class="sxs-lookup"><span data-stu-id="e3902-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="e3902-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="e3902-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="e3902-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="e3902-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="e3902-114">Nom de domaine complet (FQDN) du contrôleur de domaine actuel utilisé pour la synchronisation des Services domaine Active Directory. A une valeur d’information.</span><span class="sxs-lookup"><span data-stu-id="e3902-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="e3902-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="e3902-115">adcContent</span></span>  <br/> |<span data-ttu-id="e3902-116">image (binaire)</span><span class="sxs-lookup"><span data-stu-id="e3902-116">image (binary)</span></span>  <br/> |<span data-ttu-id="e3902-117">Cookie de synchronisation du répertoire actif.</span><span class="sxs-lookup"><span data-stu-id="e3902-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="e3902-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="e3902-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="e3902-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e3902-119">datetime</span></span>  <br/> |<span data-ttu-id="e3902-120">Horodatage avec l’heure de mise à jour de ligne.</span><span class="sxs-lookup"><span data-stu-id="e3902-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="e3902-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="e3902-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="e3902-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e3902-122">datetime</span></span>  <br/> |<span data-ttu-id="e3902-123">Temps jusqu'à ce que la ligne est verrouillée contre les modifications.</span><span class="sxs-lookup"><span data-stu-id="e3902-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="e3902-124">Cela fait partie d’un mécanisme de verrouillage logiciel qui permet de s’assurer que seul l’un des services chat effectue la synchronisation Active Directory à la fois.</span><span class="sxs-lookup"><span data-stu-id="e3902-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="e3902-125">**Clés**</span><span class="sxs-lookup"><span data-stu-id="e3902-125">**Keys**</span></span>

|<span data-ttu-id="e3902-126">**Colonne (s)**</span><span class="sxs-lookup"><span data-stu-id="e3902-126">**Column(s)**</span></span>|<span data-ttu-id="e3902-127">**Description**</span><span class="sxs-lookup"><span data-stu-id="e3902-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e3902-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e3902-128">prinGuid</span></span>  <br/> |<span data-ttu-id="e3902-129">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="e3902-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e3902-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e3902-130">prinGuid</span></span>  <br/> |<span data-ttu-id="e3902-131">Clé étrangère avec la recherche dans la table de Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="e3902-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

