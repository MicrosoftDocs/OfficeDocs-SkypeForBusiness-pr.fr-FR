---
title: Modifications apportées par la préparation du domaine dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: Le tableau suivant répertorie les entrées de contrôle d’accès (ACE) créées par la préparation du domaine à la racine du domaine. Toutes les entrées ACE sont héritées sauf mention contraire.
ms.openlocfilehash: 8a087dfbbd8b670467727803f996694a816cc065
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815542"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Modifications apportées par la préparation du domaine dans Skype entreprise Server
 
Le tableau suivant répertorie les entrées de contrôle d’accès (ACE) créées par la préparation du domaine à la racine du domaine. Toutes les entrées ACE sont héritées sauf mention contraire.
  
**ACE ajoutés à la racine du domaine**

|**MAILLOTS**|**RTCUniversal-UserReadOnly-groupe**|**RTCUniversal-ServerReadOnly-groupe**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-services**|**Utilisateurs authentifiés**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Lire le conteneur (non hérité)  <br/> |**Positive** <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lire User PropertySet-compte-restrictions  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lire Personal User PropertySet-informations  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lecture générale de User PropertySet-informations  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lire le public user PropertySet public-information  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Lecture utilisateur PropertySet RTCUserSearchProperty-Set  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |
|Lire User PropertySet RTCPropertySet  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |
|Écrire les adresses proxy de propriété utilisateur  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |
|Write User PropertySet RTCUserSearchProperty-Set  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |
|Écrire RTCPropertySet utilisateur  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |Non  <br/> |
|Lecture de PropertySet DS-réplication-obtention-modification de tous les objets Active Directory  <br/> |Non  <br/> |Non  <br/> |Non  <br/> |**Oui** <br/> |Non  <br/> |
   
Le tableau suivant répertorie les entrées de contrôle d’accès qu’il est créé dans les trois conteneurs intégrés : utilisateurs, ordinateurs et contrôleurs de domaine. Toutes les entrées ACE sont héritées sauf mention contraire.
**ACE ajoutés aux conteneurs intégrés**

|**MAILLOTS**|**RTCUniversal-UserReadOnly-groupe**|**RTCUniversal-ServerReadOnly-groupe**|
|:-----|:-----|:-----|
|Lire le conteneur (non hérité)  <br/> |**Positive** <br/> |**Oui** <br/> |
   

