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
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie contient les cookies en cours de la synchronisation de Lightweight Directory Access Protocol (LDAP).
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, pas null  <br/> |GUID principal du domaine en cours d’analyse.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Nom de domaine complet (FQDN) du contrôleur de domaine actuel utilisé pour la synchronisation des Services domaine Active Directory. A une valeur d’information.  <br/> |
|adcContent  <br/> |image (binaire)  <br/> |Cookie de synchronisation du répertoire actif.  <br/> |
|lastUpdated  <br/> |DateHeure  <br/> |Horodatage avec l’heure de mise à jour de ligne.  <br/> |
|lockedUntil  <br/> |DateHeure  <br/> |Temps jusqu'à ce que la ligne est verrouillée contre les modifications. Cela fait partie d’un mécanisme de verrouillage logiciel qui permet de s’assurer que seul l’un des services chat effectue la synchronisation Active Directory à la fois.  <br/> |
   
**Clés**

|**Colonne (s)**|**Description**|
|:-----|:-----|
|prinGuid  <br/> |Clé primaire.  <br/> |
|prinGuid  <br/> |Clé étrangère avec la recherche dans la table de Principal.prinGuid.  <br/> |
   

