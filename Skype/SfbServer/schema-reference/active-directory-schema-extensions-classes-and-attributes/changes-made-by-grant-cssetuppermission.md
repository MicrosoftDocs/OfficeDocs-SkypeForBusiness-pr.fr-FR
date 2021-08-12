---
title: Modifications apportées par Grant-CsSetupPermission dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Pour déléguer la configuration, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique, ce qui permet aux membres du groupe RTCUniversalServerAdmins de cette unité d’organisation d’installer des Skype Entreprise Server dans le domaine spécifié sans être membres du groupe Administrateurs du domaine.
ms.openlocfilehash: 32c0d48c5b6c63a38ff48e7808b8009c3ef265e6f0b6eb739094f797e47ace4d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349706"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Modifications apportées par Grant-CsSetupPermission dans Skype Entreprise Server
 
Pour déléguer la configuration, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique, ce qui permet aux membres du groupe RTCUniversalServerAdmins de cette unité d’organisation d’installer des Skype Entreprise Server dans le domaine spécifié sans être membres du groupe Administrateurs du domaine. 
  
L’applet de commande **Grant-CsSetupPermission** accorde des autorisations de groupe RTCUniversalServerAdmins sur une unité d’organisation, comme indiqué dans le tableau suivant :
  
**Autorisations accordées aux objets dans l’unité d’organisation**

|**Les autorisations s’appliquent à :**|**Les autorisations accordées sont :**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Accès particulier : <br/>  Lecture servicePrincipalName <br/>  Écriture servicePrincipalName <br/>  Suppression de l’arborescence <br/>  Réplication des modifications d’annuaire <br/> |
|Objets serviceConnectionPoint descendants  <br/> | Accès particulier : <br/>  Autorisations en lecture <br/>  Autorisations en écriture <br/>  Création de l’enfant <br/>  Suppression de l’enfant <br/>  Affichage du contenu <br/>  Écriture de propriété <br/>  Lecture de propriété <br/>  Suppression de l’arborescence <br/> |
|Objets msRTCSIP-Server descendants  <br/> | Accès particulier : <br/>  Écriture de propriété <br/>  Lecture de propriété <br/>  Suppression de l’arborescence <br/> |
|Objets msRTCSIP-WebComponents descendants  <br/> | Accès particulier : <br/>  Écriture de propriété <br/>  Lecture de propriété <br/>  Suppression de l’arborescence <br/> |
|Objets msRTCSIP-MCU descendants  <br/> | Accès particulier : <br/>  Écriture de propriété <br/>  Lecture de propriété <br/>  Suppression de l’arborescence <br/> |
|Objets msRTCSIP-MediationServer descendants  <br/> | Accès particulier : <br/>  Écriture de propriété <br/>  Lecture de propriété <br/>  Suppression de l’arborescence <br/> |
|Objets msRTCSIP-ApplicationServer descendants  <br/> | Accès particulier : <br/>  Écriture de propriété <br/>  Lecture de propriété <br/>  Suppression de l’arborescence <br/> |
|Objets msRTCSIP-ConnectionPoint descendants  <br/> | Accès particulier : <br/>  Écriture de propriété <br/>  Lecture de propriété <br/>  Suppression de l’arborescence <br/> |
|Objets Computer descendants  <br/> | Accès particulier pour serviceConnectionPoint : <br/>  Création d’objets enfants <br/>  Suppression d’objets enfants <br/>  Suppression de l’arborescence <br/>  Accès particulier pour les informations publiques : <br/>  Lecture de propriété <br/>  Accès particulier pour le nom d’hôte DNS : <br/>  Lecture de propriété <br/> |
   

