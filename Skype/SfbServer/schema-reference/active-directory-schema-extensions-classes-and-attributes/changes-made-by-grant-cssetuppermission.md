---
title: Modifications apportées par Grant-CsSetupPermission dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Pour déléguer l’installation, vous pouvez accorder au groupe RTCUniversalServerAdmins universel pour une unité d’organisation Active Directory spécifique (unité d’organisation), l’activation des membres du groupe RTCUniversalServerAdmins dans cette unité d’organisation pour installer Skype pour Business Server dans le domaine spécifié sans être membres du groupe Admins du domaine.
ms.openlocfilehash: 4b7e5eadb2083384b82eae6f6fba46d29f7b158a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907093"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Modifications apportées par Grant-CsSetupPermission dans Skype pour Business Server
 
Pour déléguer l’installation, vous pouvez accorder au groupe RTCUniversalServerAdmins universel pour une unité d’organisation Active Directory spécifique (unité d’organisation), l’activation des membres du groupe RTCUniversalServerAdmins dans cette unité d’organisation pour installer Skype pour Business Server dans le domaine spécifié sans être membres du groupe Admins du domaine. 
  
L’applet de commande **Grant-CsSetupPermission** accorde les autorisations du groupe RTCUniversalServerAdmins sur une unité d’organisation, tel que spécifié dans le tableau suivant :
  
**Autorisations accordées à des objets dans l’unité d’organisation**

|**Autorisations s’appliquent à :**|**Les autorisations accordées sont les suivants :**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Accès particulier : <br/>  Lecture servicePrincipalName <br/>  Écriture servicePrincipalName <br/>  Supprimer l’arborescence <br/>  Réplication des changements de répertoire <br/> |
|Objets serviceConnectionPoint descendants  <br/> | Accès particulier : <br/>  Autorisations de lecture <br/>  Autorisations d’écriture <br/>  Créer un enfant <br/>  Supprimer l’enfant <br/>  Contenu de liste <br/>  Propriété d’écriture <br/>  Propriété en lecture <br/>  Supprimer l’arborescence <br/> |
|Objets msRTCSIP-Server descendants  <br/> | Accès particulier : <br/>  Propriété d’écriture <br/>  Propriété en lecture <br/>  Supprimer l’arborescence <br/> |
|Objets msRTCSIP-WebComponents descendants  <br/> | Accès particulier : <br/>  Propriété d’écriture <br/>  Propriété en lecture <br/>  Supprimer l’arborescence <br/> |
|Objets msRTCSIP-MCU descendants  <br/> | Accès particulier : <br/>  Propriété d’écriture <br/>  Propriété en lecture <br/>  Supprimer l’arborescence <br/> |
|Objets msRTCSIP-MediationServer descendants  <br/> | Accès particulier : <br/>  Propriété d’écriture <br/>  Propriété en lecture <br/>  Supprimer l’arborescence <br/> |
|Objets msRTCSIP-ApplicationServer descendants  <br/> | Accès particulier : <br/>  Propriété d’écriture <br/>  Propriété en lecture <br/>  Supprimer l’arborescence <br/> |
|Objets msRTCSIP-ConnectionPoint descendants  <br/> | Accès particulier : <br/>  Propriété d’écriture <br/>  Propriété en lecture <br/>  Supprimer l’arborescence <br/> |
|Objets Computer descendants  <br/> | Accès particulier pour serviceConnectionPoint : <br/>  Créer des objets enfants <br/>  Supprimer des objets enfants <br/>  Supprimer l’arborescence <br/>  Accès particulier pour les informations publiques : <br/>  Propriété en lecture <br/>  Accès particulier pour le nom d’hôte DNS : <br/>  Propriété en lecture <br/> |
   

