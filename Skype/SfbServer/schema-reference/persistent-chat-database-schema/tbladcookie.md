---
title: tblADCookie
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actifs.
---

# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actifs.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, non null  <br/> |GUID principal du domaine en cours de surveillance.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Nom de domaine complet (FQDN) du contrôleur de domaine actuel utilisé pour la synchronisation des services de domaine Active Directory. A une valeur d’information.  <br/> |
|adcContent  <br/> |image (binaire)  <br/> |Cookie de synchronisation Active Directory.  <br/> |
|lastUpdated  <br/> |DateHeure  <br/> |Horodatage avec l’heure de mise à jour de ligne.  <br/> |
|lockedUntil  <br/> |DateHeure  <br/> |Heure jusqu’à laquelle la ligne est verrouillée pour modification. Il s’agit d’une partie d’un mécanisme de verrouillage logiciel qui garantit que la synchronisation Active Directory est effectuée par un seul des services de conversation à la fois.  <br/> |
   
**Keys**

|**Colonne(s)**|**Description**|
|:-----|:-----|
|prinGuid  <br/> |Clé primaire.  <br/> |
|prinGuid  <br/> |Clé étrangère avec recherche dans la table Principal.prinGuid.  <br/> |
   

