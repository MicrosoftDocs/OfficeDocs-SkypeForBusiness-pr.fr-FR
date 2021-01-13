---
title: tblADCookie
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actifs.
ms.openlocfilehash: 78a477399da811e674bb5a4493e61100acdd4782
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814754"
---
# <a name="tbladcookie"></a><span data-ttu-id="25762-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="25762-103">tblADCookie</span></span>
 
<span data-ttu-id="25762-104">tblADCookie contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actifs.</span><span class="sxs-lookup"><span data-stu-id="25762-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="25762-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="25762-105">**Columns**</span></span>

|<span data-ttu-id="25762-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="25762-106">**Column**</span></span>|<span data-ttu-id="25762-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="25762-107">**Type**</span></span>|<span data-ttu-id="25762-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="25762-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="25762-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="25762-109">prinGuid</span></span>  <br/> |<span data-ttu-id="25762-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="25762-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="25762-111">GUID principal du domaine en cours de surveillance.</span><span class="sxs-lookup"><span data-stu-id="25762-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="25762-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="25762-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="25762-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="25762-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="25762-114">Nom de domaine complet (FQDN) du contrôleur de domaine actuel utilisé pour la synchronisation des services de domaine Active Directory. A une valeur d’information.</span><span class="sxs-lookup"><span data-stu-id="25762-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="25762-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="25762-115">adcContent</span></span>  <br/> |<span data-ttu-id="25762-116">image (binaire)</span><span class="sxs-lookup"><span data-stu-id="25762-116">image (binary)</span></span>  <br/> |<span data-ttu-id="25762-117">Cookie de synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="25762-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="25762-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="25762-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="25762-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="25762-119">datetime</span></span>  <br/> |<span data-ttu-id="25762-120">Horodatage avec l’heure de mise à jour de ligne.</span><span class="sxs-lookup"><span data-stu-id="25762-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="25762-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="25762-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="25762-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="25762-122">datetime</span></span>  <br/> |<span data-ttu-id="25762-p101">Heure jusqu’à laquelle la ligne est verrouillée pour modification. Il s’agit d’une partie d’un mécanisme de verrouillage logiciel qui garantit que la synchronisation Active Directory est effectuée par un seul des services de conversation à la fois.</span><span class="sxs-lookup"><span data-stu-id="25762-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="25762-125">**Keys**</span><span class="sxs-lookup"><span data-stu-id="25762-125">**Keys**</span></span>

|<span data-ttu-id="25762-126">**Colonne(s)**</span><span class="sxs-lookup"><span data-stu-id="25762-126">**Column(s)**</span></span>|<span data-ttu-id="25762-127">**Description**</span><span class="sxs-lookup"><span data-stu-id="25762-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="25762-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="25762-128">prinGuid</span></span>  <br/> |<span data-ttu-id="25762-129">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="25762-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="25762-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="25762-130">prinGuid</span></span>  <br/> |<span data-ttu-id="25762-131">Clé étrangère avec recherche dans la table Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="25762-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

