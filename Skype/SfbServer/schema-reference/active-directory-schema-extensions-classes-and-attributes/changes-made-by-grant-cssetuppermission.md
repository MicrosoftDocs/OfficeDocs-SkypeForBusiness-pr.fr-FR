---
title: Modifications apportées par la subvention-CsSetupPermission dans Skype pour Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Pour déléguer l’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique (unité d’organisation), l’activation des membres du groupe RTCUniversalServerAdmins dans cette unité d’organisation pour installer Skype pour Business Server dans le domaine spécifié sans être membres du groupe Admins du domaine.
ms.openlocfilehash: 6c87ad11e0c125f2a58f2518218060b2a3636f0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Modifications apportées par la subvention-CsSetupPermission dans Skype pour Business Server
 
Pour déléguer l’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique (unité d’organisation), l’activation des membres du groupe RTCUniversalServerAdmins dans cette unité d’organisation pour installer Skype pour Business Server dans le domaine spécifié sans être membres du groupe Admins du domaine. 
  
L’applet de commande **Grant-CsSetupPermission** accorde les autorisations du groupe RTCUniversalServerAdmins sur une unité d’organisation, comme indiqué dans le tableau suivant :
  
**Autorisations accordées aux objets dans l’unité d’organisation**

|**Les autorisations s’appliquent à :**|**Autorisations accordées sont les suivantes :**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Accès spécial : <br/>  Lire le nom principal de service <br/>  Écrivez le nom principal de service <br/>  Supprimer l’arborescence <br/>  Réplication des modifications de l’annuaire <br/> |
|Objets descendants serviceConnectionPoint  <br/> | Accès spécial : <br/>  Autorisations de lecture <br/>  Autorisations d’écriture <br/>  Créer des enfants <br/>  Supprimer un enfant <br/>  Contenu de liste <br/>  Propriété d’écriture <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets descendants msRTCSIP-serveur  <br/> | Accès spécial : <br/>  Propriété d’écriture <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets descendants msRTCSIP-composants Web  <br/> | Accès spécial : <br/>  Propriété d’écriture <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets descendants msRTCSIP-MCU  <br/> | Accès spécial : <br/>  Propriété d’écriture <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets descendants msRTCSIP-MediationServer  <br/> | Accès spécial : <br/>  Propriété d’écriture <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets descendants msRTCSIP-ApplicationServer  <br/> | Accès spécial : <br/>  Propriété d’écriture <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets descendants msRTCSIP-ConnectionPoint  <br/> | Accès spécial : <br/>  Propriété d’écriture <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets ordinateur descendants  <br/> | Accès spécial pour serviceConnectionPoint : <br/>  Créer des objets enfants <br/>  Supprimer des objets enfants <br/>  Supprimer l’arborescence <br/>  Accès spécial pour les informations publiques : <br/>  Propriété de lecture <br/>  Accès spécial pour le nom d’hôte DNS : <br/>  Propriété de lecture <br/> |
   

