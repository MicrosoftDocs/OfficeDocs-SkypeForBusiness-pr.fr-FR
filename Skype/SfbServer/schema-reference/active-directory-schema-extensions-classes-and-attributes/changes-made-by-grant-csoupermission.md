---
title: Modifications apportées par Grant-CsOUPermission dans Skype pour Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Pour déléguer l’administration de serveur d’entreprise Skype, vous pouvez ajouter des autorisations pour les unités d’organisation (UO) spécifiées afin que les membres des groupes universels RTC créés par la préparation de forêt peuvent accéder les unités d’organisation sans être membres du groupe Admins du domaine.
ms.openlocfilehash: 304f5d905f8839224013a2ce674b98405fd9ce8e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876809"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Modifications apportées par Grant-CsOUPermission dans Skype pour Business Server
 
Pour déléguer l’administration de serveur d’entreprise Skype, vous pouvez ajouter des autorisations pour les unités d’organisation (UO) spécifiées afin que les membres des groupes universels RTC créés par la préparation de forêt peuvent accéder les unités d’organisation sans être membres du groupe Admins du domaine. 
  
L’applet de commande **Grant-CsOuPermission** accorde des autorisations à des objets dans l’unité d’organisation spécifiée comme indiqué dans les tableaux suivants.
  
## <a name="granting-permission-for-user-objects"></a>Octroi d’une autorisation pour les objets utilisateur

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets utilisateur dans une unité d’organisation, groupes se voient octroyer les autorisations comme indiqué dans le tableau suivant.
  
**Autorisations octroyées pour les objets utilisateur**

|**Groupe**|**autorisation**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des changements de répertoire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lire RTCUserSearchPropertySet  <br/> Lire RTCUserProvisioningPropertySet  <br/> Lire RTCPropertySet  <br/> Lire les informations publiques  <br/> Lire les informations générales  <br/> Lire les Restrictions de compte d’utilisateur  <br/> |Objets d’utilisateur descendant  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire RTCUserSearchPropertySet  <br/> Écrire msExchUCVoiceMailSettings  <br/> Écrire RTCUserProvisioningPropertySet  <br/> Écrire RTCPropertySet  <br/> Écrire proxyAddresses  <br/> |Objets d’utilisateur descendant  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Octroi d’une autorisation pour les objets ordinateur

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets ordinateur dans une unité d’organisation, groupes se voient octroyer les autorisations comme indiqué dans le tableau suivant.
  
**Autorisations octroyées pour les objets ordinateur**

|**Groupe**|**autorisation**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des changements de répertoire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lire les informations publiques  <br/> Lecture validée---nom d’hôte DNS  <br/> |Objets Computer descendants  <br/> |
|RTCUniversalUserAdmins  <br/> |Lire les informations publiques  <br/> Lecture validée---nom d’hôte DNS  <br/> |Objets Computer descendants  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Octroi d’autorisation pour les objets Contact ou AppContact

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets Contact ou appcontact sur une unité d’organisation, groupes se voient octroyer les autorisations comme indiqué dans le tableau suivant.
  
**Autorisations octroyées pour les objets Contact ou AppContact**

|**Groupe**|**autorisation**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des changements de répertoire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lire RTCUserSearchPropertySet  <br/> Lire RTCUserProvisioningPropertySet  <br/> Lire RTCPropertySet  <br/> Lire les informations publiques  <br/> Lire les informations générales  <br/> Lire les informations personnelles  <br/> Lire les Restrictions de compte d’utilisateur  <br/> |Objets Contact descendant  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire RTCUserSearchPropertySet  <br/> Écrire otherIpPhone  <br/> Écrire displayName  <br/> Écrire la description  <br/> Écrire telephoneNumber  <br/> Écrire msExchUCVoiceMailSettings  <br/> Écrire RTCUserProvisioningPropertySet  <br/> Écrire RTCPropertySet  <br/> Écrire proxyAddresses  <br/> |Objets Contact descendant  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Octroi d’une autorisation pour les objets périphérique

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets périphérique sur une unité d’organisation, groupes se voient octroyer les autorisations comme indiqué dans le tableau suivant.
  
**Autorisations octroyées pour les objets périphérique**

|**Groupe**|**autorisation**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des changements de répertoire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lire RTCUserSearchPropertySet  <br/> Lire RTCUserProvisioningPropertySet  <br/> Lire RTCPropertySet  <br/> Lire les informations publiques  <br/> Lire les informations personnelles  <br/> Lire les informations générales  <br/> Lire les Restrictions de compte d’utilisateur  <br/> |Objets Contact descendant  <br/> |
|RTCUniversalUserAdmins  <br/> |Créer un enfant  <br/> Supprimer l’enfant  <br/> Supprimer l’arborescence  <br/> |Contact  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire displayName  <br/> Écrire la description  <br/> Écrire telephoneNumber  <br/> |Objets d’utilisateur descendant  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire RTCUserSearchPropertySet  <br/> Écrire otherIpPhone  <br/> Écrire displayName  <br/> Écrire la description  <br/> Écrire telephoneNumber  <br/> Écrire msExchUCVoiceMailSettings  <br/> Écrire RTCUserProvisioningPropertySet  <br/> Écrire RTCPropertySet  <br/> Écrire proxyAddresses  <br/> |Objets Contact descendant  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Octroi d’une autorisation pour les objets InetOrgPerson

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets InetOrgPerson sur une unité d’organisation, groupes se voient octroyer les autorisations comme indiqué dans le tableau suivant.
  
**Autorisations octroyées pour les objets InetOrgPerson**

|**Groupe**|**autorisation**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des changements de répertoire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lire RTCUserSearchPropertySet  <br/> Lire RTCUserProvisioningPropertySet  <br/> Lire RTCPropertySet  <br/> Lire les informations personnelles  <br/> Lire les informations publiques  <br/> Lire les informations générales  <br/> Lire les Restrictions de compte d’utilisateur  <br/> |Objets inetOrgPerson descendant  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire RTCUserSearchPropertySet  <br/> Écrire RTCUserProvisioningPropertySet  <br/> Écrire RTCPropertySet  <br/> Écrire proxyAddresses  <br/> |Objets inetOrgPerson descendant  <br/> |
   

