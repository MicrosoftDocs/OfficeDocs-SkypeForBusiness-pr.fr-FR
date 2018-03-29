---
title: Modifications apportées par la subvention-CsOUPermission dans Skype pour Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Pour déléguer Skype pour l’administration de serveur d’entreprise, vous pouvez ajouter des autorisations aux unités d’organisation spécifiées (ou) afin que les membres des groupes universels RTC créés en préparation de la forêt peuvent accéder aux unités d’organisation sans être membres du groupe Admins du domaine.
ms.openlocfilehash: 1313394248da2dcaeb9843bd689b2e2da3c51f96
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Modifications apportées par la subvention-CsOUPermission dans Skype pour Business Server
 
Pour déléguer Skype pour l’administration de serveur d’entreprise, vous pouvez ajouter des autorisations aux unités d’organisation spécifiées (ou) afin que les membres des groupes universels RTC créés en préparation de la forêt peuvent accéder aux unités d’organisation sans être membres du groupe Admins du domaine. 
  
L’applet de commande **Grant-CsOuPermission** accorde des autorisations à des objets dans l’unité d’organisation spécifiée comme indiqué dans les tableaux ci-dessous.
  
## <a name="granting-permission-for-user-objects"></a>L’octroi de l’autorisation pour les objets utilisateur

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets utilisateur dans une unité d’organisation, les groupes sont autorisés comme indiqué dans le tableau suivant.
  
**Autorisations accordées sur les objets de l’utilisateur**

|**Groupe**|**Autorisation**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des modifications de l’annuaire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lecture RTCUserSearchPropertySet  <br/> Lecture RTCUserProvisioningPropertySet  <br/> En lecture RTCPropertySet  <br/> Lire les informations publiques  <br/> Lire les informations générales  <br/> Lire les Restrictions de compte utilisateur  <br/> |Objets utilisateur descendants  <br/> |
|RTCUniversalUserAdmins  <br/> |Écriture RTCUserSearchPropertySet  <br/> Écriture msExchUCVoiceMailSettings  <br/> Écriture RTCUserProvisioningPropertySet  <br/> Écriture RTCPropertySet  <br/> Écrire adresses proxyAddresses  <br/> |Objets utilisateur descendants  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>L’octroi de l’autorisation pour les objets ordinateur

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets ordinateur dans une unité d’organisation, les groupes sont autorisés comme indiqué dans le tableau suivant.
  
**Autorisations accordées sur les objets de l’ordinateur**

|**Groupe**|**Autorisation**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des modifications de l’annuaire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lire les informations publiques  <br/> Lecture validée---nom d’hôte DNS  <br/> |Objets ordinateur descendants  <br/> |
|RTCUniversalUserAdmins  <br/> |Lire les informations publiques  <br/> Lecture validée---nom d’hôte DNS  <br/> |Objets ordinateur descendants  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>L’octroi de l’autorisation pour les objets de AppContact ou de Contact

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour des objets Contact ou AppContact sur une unité d’organisation, les groupes sont autorisés comme indiqué dans le tableau suivant.
  
**Autorisations accordées sur les objets de AppContact ou de Contact**

|**Groupe**|**Autorisation**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des modifications de l’annuaire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lecture RTCUserSearchPropertySet  <br/> Lecture RTCUserProvisioningPropertySet  <br/> En lecture RTCPropertySet  <br/> Lire les informations publiques  <br/> Lire les informations générales  <br/> Lire des informations personnelles  <br/> Lire les Restrictions de compte utilisateur  <br/> |Objets descendants du Contact  <br/> |
|RTCUniversalUserAdmins  <br/> |Écriture RTCUserSearchPropertySet  <br/> Écriture otherIpPhone  <br/> Écrire displayName  <br/> Écrire la description  <br/> Écrire le numéro de téléphone  <br/> Écriture msExchUCVoiceMailSettings  <br/> Écriture RTCUserProvisioningPropertySet  <br/> Écriture RTCPropertySet  <br/> Écrire adresses proxyAddresses  <br/> |Objets descendants du Contact  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>L’octroi de l’autorisation pour les objets de périphérique

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets de périphérique sur une unité d’organisation, les groupes sont autorisés comme indiqué dans le tableau suivant.
  
**Autorisations accordées sur les objets de périphérique**

|**Groupe**|**Autorisation**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des modifications de l’annuaire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lecture RTCUserSearchPropertySet  <br/> Lecture RTCUserProvisioningPropertySet  <br/> En lecture RTCPropertySet  <br/> Lire les informations publiques  <br/> Lire des informations personnelles  <br/> Lire les informations générales  <br/> Lire les Restrictions de compte utilisateur  <br/> |Objets descendants du Contact  <br/> |
|RTCUniversalUserAdmins  <br/> |Créer des enfants  <br/> Supprimer un enfant  <br/> Supprimer l’arborescence  <br/> |Contact  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire displayName  <br/> Écrire la description  <br/> Écrire le numéro de téléphone  <br/> |Objets utilisateur descendants  <br/> |
|RTCUniversalUserAdmins  <br/> |Écriture RTCUserSearchPropertySet  <br/> Écriture otherIpPhone  <br/> Écrire displayName  <br/> Écrire la description  <br/> Écrire le numéro de téléphone  <br/> Écriture msExchUCVoiceMailSettings  <br/> Écriture RTCUserProvisioningPropertySet  <br/> Écriture RTCPropertySet  <br/> Écrire adresses proxyAddresses  <br/> |Objets descendants du Contact  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>L’octroi de l’autorisation pour les objets InetOrgPerson

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets InetOrgPerson sur une unité d’organisation, les groupes sont autorisés comme indiqué dans le tableau suivant.
  
**Autorisations accordées sur les objets InetOrgPerson**

|**Groupe**|**Autorisation**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des modifications de l’annuaire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenu de liste  <br/> Lire toutes les propriétés  <br/> Autorisations de lecture  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lecture RTCUserSearchPropertySet  <br/> Lecture RTCUserProvisioningPropertySet  <br/> En lecture RTCPropertySet  <br/> Lire des informations personnelles  <br/> Lire les informations publiques  <br/> Lire les informations générales  <br/> Lire les Restrictions de compte utilisateur  <br/> |Objets inetOrgPerson descendant  <br/> |
|RTCUniversalUserAdmins  <br/> |Écriture RTCUserSearchPropertySet  <br/> Écriture RTCUserProvisioningPropertySet  <br/> Écriture RTCPropertySet  <br/> Écrire adresses proxyAddresses  <br/> |Objets inetOrgPerson descendant  <br/> |
   

