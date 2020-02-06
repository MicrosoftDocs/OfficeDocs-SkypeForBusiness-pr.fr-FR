---
title: Modifications apportées par Grant-CsSetupPermission dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Pour déléguer le programme d’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique (UO), ce qui permet aux membres du groupe RTCUniversalServerAdmins dans cette unité d’organisation d’installer Skype entreprise Server dans le domaine spécifié sans être membre du groupe administrateurs de domaine.
ms.openlocfilehash: 844cfa586523750b804564482146c0e76b39fc38
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815512"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Modifications apportées par Grant-CsSetupPermission dans Skype entreprise Server
 
Pour déléguer le programme d’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique (UO), ce qui permet aux membres du groupe RTCUniversalServerAdmins dans cette unité d’organisation d’installer Skype entreprise Server dans le domaine spécifié sans être membre du groupe administrateurs de domaine. 
  
L’applet de commande **Grant-CsSetupPermission** accorde aux autorisations de groupe RTCUniversalServerAdmins sur une unité d’organisation, comme indiqué dans le tableau suivant :
  
**Autorisations accordées aux objets dans l’unité d’organisation**

|**Les autorisations s’appliquent à :**|**Les autorisations accordées sont les suivantes :**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Accès spécial : <br/>  Lire servicePrincipalName <br/>  Écrire le servicePrincipalName <br/>  Supprimer l’arborescence <br/>  Répliquer les modifications de l’annuaire <br/> |
|Objets serviceConnectionPoint descendants  <br/> | Accès spécial : <br/>  Autorisations de lecture <br/>  Autorisations d’écriture <br/>  Créer un enfant <br/>  Supprimer un enfant <br/>  Contenu de la liste <br/>  Propriété Write <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets enfants msRTCSIP-Server  <br/> | Accès spécial : <br/>  Propriété Write <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets enfants msRTCSIP-webcomposants  <br/> | Accès spécial : <br/>  Propriété Write <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets descendants msRTCSIP-MCU  <br/> | Accès spécial : <br/>  Propriété Write <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets MediationServer en descendant  <br/> | Accès spécial : <br/>  Propriété Write <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets ApplicationServer en descendant  <br/> | Accès spécial : <br/>  Propriété Write <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets descendants de msRTCSIP-ConnectionPoint  <br/> | Accès spécial : <br/>  Propriété Write <br/>  Propriété de lecture <br/>  Supprimer l’arborescence <br/> |
|Objets ordinateur descendants  <br/> | Accès spécial pour serviceConnectionPoint : <br/>  Créer des objets enfants <br/>  Supprimer des objets enfants <br/>  Supprimer l’arborescence <br/>  Accès spécial pour les informations publiques : <br/>  Propriété de lecture <br/>  Accès spécial pour le nom d’hôte DNS : <br/>  Propriété de lecture <br/> |
   

