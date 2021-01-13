---
title: Modifications apportées par la préparation du domaine dans Skype Entreprise Server
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
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: Le tableau ci-après répertorie les entrées de contrôle d’accès créées par la préparation de domaine sur la racine de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.
ms.openlocfilehash: 46eaedb25ca245a5426314a8118be7443fb612e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831904"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Modifications apportées par la préparation du domaine dans Skype Entreprise Server
 
Le tableau ci-après répertorie les entrées de contrôle d’accès créées par la préparation de domaine sur la racine de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.
  
**Entrées de contrôle d’accès ajoutées à la racine de domaine**

|**moteur ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**Authenticated-Users**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Read Container (non héritée)  <br/> |**Oui** <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Read User PropertySet User-Account-Restrictions  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Read User PropertySet Personal-Information  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Read User PropertySet General-Information  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Read User PropertySet Public-Information  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Read User PropertySet RTCUserSearchProperty-Set  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |
|Read User PropertySet RTCPropertySet  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Write User Property Proxy-Addresses  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |
|Write User PropertySet RTCUserSearchProperty-Set  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |
|Write User PropertySet RTCPropertySet  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |
|Read PropertySet DS-Replication-Get-Changes de tous les objets Active Directory  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |
   
Le tableau suivant répertorie les entrées de contrôle d’accès créées par la préparation de domaine dans les trois conteneurs intégrés : Utilisateurs, Ordinateurs et Contrôleurs de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.
**Entrées de contrôle d’accès ajoutées aux conteneurs intégrés**

|**moteur ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|Read Container (non héritée)  <br/> |**Oui** <br/> |**Oui** <br/> |
   

