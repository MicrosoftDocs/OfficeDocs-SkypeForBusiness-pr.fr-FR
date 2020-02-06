---
title: Modifications apportées par Grant-CsOUPermission dans Skype entreprise Server
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
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Pour déléguer l’administration de Skype entreprise Server, vous pouvez ajouter des autorisations d’accès à des unités d’organisation (UO) spécifiques de sorte que les membres des groupes universels RTC créés par la préparation de la forêt puissent accéder aux UO sans être membres du groupe administrateurs de domaine.
ms.openlocfilehash: 8342d1801d2df91f940f02e8bfc05c3c5b91c4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815522"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Modifications apportées par Grant-CsOUPermission dans Skype entreprise Server
 
Pour déléguer l’administration de Skype entreprise Server, vous pouvez ajouter des autorisations d’accès à des unités d’organisation (UO) spécifiques de sorte que les membres des groupes universels RTC créés par la préparation de la forêt puissent accéder aux UO sans être membres du groupe administrateurs de domaine. 
  
L’applet **de commande Grant-CsOuPermission** accorde des autorisations aux objets de l’unité d’organisation spécifiée, comme indiqué dans les tableaux suivants.
  
## <a name="granting-permission-for-user-objects"></a>Octroi d’autorisations pour les objets utilisateur

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets utilisateur sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.
  
**Autorisations accordées pour les objets utilisateur**

|**Groupe**|**Permission**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Répliquer les modifications de l’annuaire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de la liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de la liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lecture de RTCUserSearchPropertySet  <br/> Lecture de RTCUserProvisioningPropertySet  <br/> Lecture de RTCPropertySet  <br/> Lecture publique-informations  <br/> Lecture générale-informations  <br/> Lire le compte d’utilisateur-restrictions  <br/> |Objets utilisateur descendants  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire RTCUserSearchPropertySet  <br/> Écrire msExchUCVoiceMailSettings  <br/> Écrire RTCUserProvisioningPropertySet  <br/> Écrire RTCPropertySet  <br/> Écrire proxyAddresses  <br/> |Objets utilisateur descendants  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Octroi d’autorisations pour les objets ordinateur

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets ordinateur sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.
  
**Autorisations accordées pour les objets ordinateur**

|**Groupe**|**Permission**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Répliquer les modifications de l’annuaire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de la liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de la liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lecture publique-informations  <br/> Lecture validée de DNS-nom d’hôte-nom  <br/> |Objets ordinateur descendants  <br/> |
|RTCUniversalUserAdmins  <br/> |Lecture publique-informations  <br/> Lecture validée de DNS-nom d’hôte-nom  <br/> |Objets ordinateur descendants  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Octroi d’autorisations de contact ou d’objets AppContact

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets de contact ou les objets AppContact sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.
  
**Autorisations accordées pour les objets contact ou AppContact**

|**Groupe**|**Permission**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Répliquer les modifications de l’annuaire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de la liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de la liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lecture de RTCUserSearchPropertySet  <br/> Lecture de RTCUserProvisioningPropertySet  <br/> Lecture de RTCPropertySet  <br/> Lecture publique-informations  <br/> Lecture générale-informations  <br/> Lire les informations personnelles  <br/> Lire le compte d’utilisateur-restrictions  <br/> |Objets contact descendants  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire RTCUserSearchPropertySet  <br/> Écrire otherIpPhone  <br/> Écrire displayName  <br/> Entrer une description  <br/> Écrire telephoneNumber  <br/> Écrire msExchUCVoiceMailSettings  <br/> Écrire RTCUserProvisioningPropertySet  <br/> Écrire RTCPropertySet  <br/> Écrire proxyAddresses  <br/> |Objets contact descendants  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Octroi d’autorisations pour les objets appareil

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets d’appareil sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.
  
**Autorisations accordées pour les objets appareil**

|**Groupe**|**Permission**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Répliquer les modifications de l’annuaire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de la liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de la liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lecture de RTCUserSearchPropertySet  <br/> Lecture de RTCUserProvisioningPropertySet  <br/> Lecture de RTCPropertySet  <br/> Lecture publique-informations  <br/> Lire les informations personnelles  <br/> Lecture générale-informations  <br/> Lire le compte d’utilisateur-restrictions  <br/> |Objets contact descendants  <br/> |
|RTCUniversalUserAdmins  <br/> |Créer un enfant  <br/> Supprimer un enfant  <br/> Supprimer l’arborescence  <br/> |Locuteur  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire displayName  <br/> Entrer une description  <br/> Écrire telephoneNumber  <br/> |Objets utilisateur descendants  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire RTCUserSearchPropertySet  <br/> Écrire otherIpPhone  <br/> Écrire displayName  <br/> Entrer une description  <br/> Écrire telephoneNumber  <br/> Écrire msExchUCVoiceMailSettings  <br/> Écrire RTCUserProvisioningPropertySet  <br/> Écrire RTCPropertySet  <br/> Écrire proxyAddresses  <br/> |Objets contact descendants  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Octroi d’autorisations pour les objets InetOrgPerson

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets InetOrgPerson sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.
  
**Autorisations accordées pour les objets InetOrgPerson**

|**Groupe**|**Permission**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Répliquer les modifications de l’annuaire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de la liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de la liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lecture de RTCUserSearchPropertySet  <br/> Lecture de RTCUserProvisioningPropertySet  <br/> Lecture de RTCPropertySet  <br/> Lire les informations personnelles  <br/> Lecture publique-informations  <br/> Lecture générale-informations  <br/> Lire le compte d’utilisateur-restrictions  <br/> |Objets inetOrgPerson descendants  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire RTCUserSearchPropertySet  <br/> Écrire RTCUserProvisioningPropertySet  <br/> Écrire RTCPropertySet  <br/> Écrire proxyAddresses  <br/> |Objets inetOrgPerson descendants  <br/> |
   

