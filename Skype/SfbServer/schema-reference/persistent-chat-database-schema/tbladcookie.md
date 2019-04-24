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
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie contient les cookies de synchronisation Lightweight Directory Access Protocol (LDAP).
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, non null  <br/> |GUID principal du domaine en cours d’analyse.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Nom de domaine complet (FQDN) du contrôleur de domaine en cours utilisé pour la synchronisation des Services de domaine Active Directory. A la valeur d’information.  <br/> |
|adcContent  <br/> |image (binaire)  <br/> |Cookie de synchronisation d’annuaires actif.  <br/> |
|lastUpdated  <br/> |DateHeure  <br/> |Horodatage avec l’heure de mise à jour de ligne.  <br/> |
|lockedUntil  <br/> |DateHeure  <br/> |Temps jusqu'à ce que la ligne est verrouillée contre les modifications. Il fait partie d’un mécanisme de verrouillage logiciel qui garantit que seuls des services de conversation fait la synchronisation Active Directory à la fois.  <br/> |
   
**Clés**

|**Colonnes**|**Description**|
|:-----|:-----|
|prinGuid  <br/> |Clé primaire.  <br/> |
|prinGuid  <br/> |Clé étrangère avec recherche dans la table Principal.prinGuid.  <br/> |
   

