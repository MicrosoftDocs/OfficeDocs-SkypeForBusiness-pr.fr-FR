---
title: Modifications apportées par Grant-CsOUPermission dans Skype Entreprise Server
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
ms.localizationpriority: medium
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Pour déléguer l’administration Skype Entreprise Server, vous pouvez ajouter des autorisations aux unités d’organisation spécifiées afin que les membres des groupes universels RTC créés par la préparation de la forêt peuvent accéder aux unités d’organisation sans être membres du groupe Administrateurs du domaine.
ms.openlocfilehash: f700b03f95be05e00d4e5eb032d9dd50ceb1352b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613904"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Modifications apportées par Grant-CsOUPermission dans Skype Entreprise Server
 
Pour déléguer l’administration Skype Entreprise Server, vous pouvez ajouter des autorisations aux unités d’organisation spécifiées afin que les membres des groupes universels RTC créés par la préparation de la forêt peuvent accéder aux unités d’organisation sans être membres du groupe Administrateurs du domaine. 
  
La cmdlet **Grant-CsOuPermission** des autorisations à des objets dans des unités d’organisation définies, comme indiqué dans les tableaux suivants.
  
## <a name="granting-permission-for-user-objects"></a>Octroi d’une autorisation pour les objets utilisateur

Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets utilisateur ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.
  
**Autorisations octroyées pours les objets utilisateur**

|**Group**|**Permission**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des modifications du répertoire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Lister le contenu  <br/> Lire toutes les propriétés  <br/> Lire les autorisations  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lister le contenu  <br/> Lire toutes les propriétés  <br/> Lire les autorisations  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lire RTCUserSearchPropertySet  <br/> Lire RTCUserProvisioningPropertySet  <br/> Lire RTCPropertySet  <br/> Lire les informations publiques  <br/> Lire les informations générales  <br/> Lire les restrictions de compte utilisateur  <br/> |Objets d’utilisateur descendant  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire RTCUserSearchPropertySet  <br/> Écrire msExchUCVoiceMailSettings  <br/> Écrire RTCUserProvisioningPropertySet  <br/> Écrire RTCPropertySet  <br/> Écrire proxyAddresses  <br/> |Objets d’utilisateur descendant  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Octroi d’une autorisation pour les objets utilisateur

Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets ordinateur ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.
  
**Autorisations octroyées pour les objets ordinateur**

|**Group**|**Permission**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des modifications du répertoire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Lister le contenu  <br/> Lire toutes les propriétés  <br/> Lire les autorisations  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lister le contenu  <br/> Lire toutes les propriétés  <br/> Lire les autorisations  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lire les informations publiques  <br/> Lire le nom d’hôte DNS validé  <br/> |Objets de l’ordinateur descendant  <br/> |
|RTCUniversalUserAdmins  <br/> |Lire les informations publiques  <br/> Lire le nom d’hôte DNS validé  <br/> |Objets de l’ordinateur descendant  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Octroi d’autorisation pour les objets contact ou AppContact

Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets contact ou AppContact sur une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.
  
**Autorisations octroyées pour les objets contact ou AppContact**

|**Group**|**Permission**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des modifications du répertoire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Lister le contenu  <br/> Lire toutes les propriétés  <br/> Lire les autorisations  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lister le contenu  <br/> Lire toutes les propriétés  <br/> Lire les autorisations  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lire RTCUserSearchPropertySet  <br/> Lire RTCUserProvisioningPropertySet  <br/> Lire RTCPropertySet  <br/> Lire les informations publiques  <br/> Lire les informations générales  <br/> Lire les informations publiques  <br/> Lire les restrictions de compte utilisateur  <br/> |Objets du contact descendant  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire RTCUserSearchPropertySet  <br/> Écrire otherIpPhone  <br/> Écrire displayName  <br/> Écrire la description  <br/> Écrire telephoneNumber  <br/> Écrire msExchUCVoiceMailSettings  <br/> Écrire RTCUserProvisioningPropertySet  <br/> Écrire RTCPropertySet  <br/> Écrire proxyAddresses  <br/> |Objets du contact descendant  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Octroi d’une autorisation pour les objets périphérique

Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets périphérique ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.
  
**Autorisations octroyées pours les objets périphérique**

|**Group**|**Permission**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des modifications du répertoire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Lister le contenu  <br/> Lire toutes les propriétés  <br/> Lire les autorisations  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lister le contenu  <br/> Lire toutes les propriétés  <br/> Lire les autorisations  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lire RTCUserSearchPropertySet  <br/> Lire RTCUserProvisioningPropertySet  <br/> Lire RTCPropertySet  <br/> Lire les informations publiques  <br/> Lire les informations publiques  <br/> Lire les informations générales  <br/> Lire les restrictions de compte utilisateur  <br/> |Objets du contact descendant  <br/> |
|RTCUniversalUserAdmins  <br/> |Créer un enfant  <br/> Supprimer un enfant  <br/> Supprimer l’arborescence  <br/> |Contact  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire displayName  <br/> Écrire la description  <br/> Écrire telephoneNumber  <br/> |Objets d’utilisateur descendant  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire RTCUserSearchPropertySet  <br/> Écrire otherIpPhone  <br/> Écrire displayName  <br/> Écrire la description  <br/> Écrire telephoneNumber  <br/> Écrire msExchUCVoiceMailSettings  <br/> Écrire RTCUserProvisioningPropertySet  <br/> Écrire RTCPropertySet  <br/> Écrire proxyAddresses  <br/> |Objets du contact descendant  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Octroi d’une autorisation pour les objets InetOrgPerson

Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets InetOrgPerson ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.
  
**Autorisations octroyées pour les objets InetOrgPerson**

|**Group**|**Permission**|**S’applique à**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Réplication des modifications du répertoire  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Lister le contenu  <br/> Lire toutes les propriétés  <br/> Lire les autorisations  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lister le contenu  <br/> Lire toutes les propriétés  <br/> Lire les autorisations  <br/> |Cet objet uniquement  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lire RTCUserSearchPropertySet  <br/> Lire RTCUserProvisioningPropertySet  <br/> Lire RTCPropertySet  <br/> Lire les informations publiques  <br/> Lire les informations publiques  <br/> Lire les informations générales  <br/> Lire les restrictions de compte utilisateur  <br/> |Objets du InetOrgPerson descendant  <br/> |
|RTCUniversalUserAdmins  <br/> |Écrire RTCUserSearchPropertySet  <br/> Écrire RTCUserProvisioningPropertySet  <br/> Écrire RTCPropertySet  <br/> Écrire proxyAddresses  <br/> |Objets du InetOrgPerson descendant  <br/> |
   

