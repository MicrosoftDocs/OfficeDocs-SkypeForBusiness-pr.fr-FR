---
title: Planifier plusieurs numéros d’urgence dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Consultez cette rubrique pour découvrir comment planifier plusieurs numéros d’urgence dans Skype entreprise Server.
ms.openlocfilehash: 10b6d02391fbf1ac7af1ae5233261c36fd2fd6ab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983019"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planifier plusieurs numéros d’urgence dans Skype entreprise Server
 
Consultez cette rubrique pour découvrir comment planifier plusieurs numéros d’urgence dans Skype entreprise Server.
  
Skype entreprise Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Plusieurs numéros d’urgence sont une nouvelle fonctionnalité introduite dans la mise à jour cumulative de juin 2016. Tandis que les États-Unis ont un seul numéro d’urgence, 911, de nombreux pays prennent en charge plusieurs numéros d’urgence. Le Royaume-Uni, par exemple, prend en charge à la fois 999, le numéro d’urgence propre au Royaume-Uni et 112, le numéro d’urgence de l’Union européenne. 
  
Cette fonctionnalité est également utile pour les prestataires de soins de santé aux États-Unis qui souhaitent bénéficier d’une prise en charge de l’itinérance pour plusieurs codes d’urgence bleus.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Plusieurs numéros d’urgence et stratégies d’emplacement

Vous configurez les appels d’urgence en créant des stratégies d’emplacement qui définissent le mode d’implémentation des appels d’urgence. Vous utilisez la stratégie d’emplacement pour définir le numéro qui constitue un appel d’urgence, par exemple, 911 aux États-Unis ; 999 et 112 au Royaume-Uni. La stratégie d’emplacement détermine si un utilisateur est activé pour les appels d’urgence et, si c’est le cas, le comportement d’un appel d’urgence. Vous pouvez également définir si la sécurité de l’entreprise doit être automatiquement notifiée et comment l’appel doit être acheminé.
  
Pour plus d’informations sur la définition et la modification d’une stratégie d’emplacement, voir [plan location Policies for Skype for Business Server](location-policies.md) et [Create location Policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). Ces rubriques décrivent les concepts relatifs aux stratégies d’emplacement ; Toutefois, vous devez suivre les instructions de la page [configurer plusieurs numéros d’urgence dans Skype entreprise](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) pour configurer plusieurs numéros d’urgence.
  
Lors de la planification de plusieurs numéros d’urgence, gardez les points suivants à l’esprit :
  
- Avec la mise à jour cumulative de juin 2016, vous pouvez définir jusqu’à 5 numéros d’urgence pour une stratégie d’emplacement donnée. Avec la mise à jour cumulative de novembre 2016, ce nombre augmente jusqu’à 100.
    
    > [!NOTE]
    > Si vous n’avez pas encore effectué la mise à niveau vers la mise à jour cumulative de novembre 2016, consultez la rubrique [mises à jour vers Skype entreprise Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Pour chaque numéro d’urgence, vous pouvez spécifier zéro ou plusieurs masques de numérotation d’urgence, qui sont uniques à une stratégie d’emplacement donnée.
    
    Un masque de numérotation est un nombre que vous souhaitez traduire en valeur de numéro de téléphone d’urgence lorsqu’il est composé. Par exemple, supposons que vous entriez la valeur 212 dans ce champ et que le champ numéro de téléphone d’urgence a une valeur de 911. Lorsqu’un utilisateur compose 212, le numéro est traduit en 911. Cela permet de composer d’autres numéros d’urgence et de faire en sorte que l’appel atteigne les services d’urgence (par exemple, si une personne d’un pays ou d’une région avec un numéro d’urgence différent tente de composer le numéro de ce pays ou de cette région plutôt que le numéro de la pays ou région où ils se trouvent actuellement). Vous pouvez définir plusieurs masques d’appel d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212;414. La limite de chaîne pour un masque de numérotation est de 100 caractères. Chaque caractère doit être un chiffre compris entre 0 et 9.
    
- Chaque stratégie d’emplacement dispose d’une seule utilisation du réseau téléphonique commuté (PSTN) qui permet de déterminer l’itinéraire des communications vocales utilisé pour acheminer les appels d’urgence des clients à l’aide de cette stratégie. L’utilisation peut avoir un seul itinéraire par numéro d’urgence.
    
- Si les paramètres EmergencyNumbers et DialString sont définis pour une stratégie d’emplacement et que le client prend en charge plusieurs numéros d’urgence, le numéro d’urgence prend la priorité. Si le client ne prend pas en charge plusieurs numéros d’urgence, la chaîne de numérotation d’urgence est utilisée.
    
- Pour plus d’informations sur les clients Skype entreprise et Lync prenant en charge la réception de plusieurs numéros d’urgence, masques de numérotation et utilisations du réseau téléphonique commuté (RTC), voir [prise en charge des clients](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Vous ne pouvez pas configurer plusieurs numéros d’urgence à l’aide du panneau de configuration Skype entreprise. Vous devez utiliser PowerShell pour configurer plusieurs numéros d’urgence. 
  
Avant de configurer plusieurs numéros d’urgence, gardez les points suivants à l’esprit :
  
- Pour configurer plusieurs numéros d’urgence, vous devez utiliser la cmdlet New-applet csemergencynumber et définir des stratégies d’emplacement qui prennent en charge plusieurs numéros d’urgence en spécifiant le paramètre EmergencyNumbers avec les cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) et [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- Si des numéros existants sont définis à l’aide de la cmdlet Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask, les valeurs spécifiées avec le paramètre EmergencyNumbers prévalent sur l’ancien value. Autrement dit, les valeurs des paramètres EmergencyDialString et EmergencyDialMask sont ignorées.
    
- Si des numéros existants sont définis à l’aide de la cmdlet Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask, *et que vous ne configurez pas de nouveaux numéros d’urgence* , les numéros existants continueront à être utilisés.
    
- Pour que la fonctionnalité de plusieurs numéros d’urgence fonctionne, les versions des clients que vous exécutez doivent pouvoir prendre en charge la nouvelle fonctionnalité. Les clients plus anciens continueront à utiliser les anciennes valeurs spécifiées par les cmdlets Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask. 
    
- Si les utilisateurs composent un numéro qui correspond à la chaîne de numérotation, aucun masque de numérotation n’est nécessaire. Par exemple, si le numéro composé par un utilisateur est 911, la chaîne de numérotation est 911 et aucun masque n’est requis. 
    
Pour plus d’informations sur la configuration de plusieurs numéros d’urgence, reportez-vous à la rubrique [configure multiple Emergency Numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
Le tableau suivant présente des exemples de stratégies d’emplacement (dans le cadre de l’exemple, tous les attributs ne sont pas affichés) :
  

|**Nom de la stratégie d’emplacement**|**E911 activé**|**Chaîne de numérotation d’urgence**|**Masque de numérotation**|**Numéros d’urgence**|**Utilisation PSTN**|**Emplacement requis**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis  <br/> |Oui  <br/> |911  <br/> | 112 ; 999 <br/> ||USEmergency  <br/> |Oui  <br/> |
|États-Unis-hôpital  <br/> |Oui  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Oui  <br/> |
|Londres  <br/> |Oui  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911 ; 117 ; 118  <br/> |GBEmergency  <br/> |Non  <br/> |
|Inde  <br/> |Oui  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Non  <br/> |
   
 **États-Unis** : il n’est pas nécessaire d’avoir plusieurs numéros d’urgence. Aux États-Unis, vous utilisez les anciennes configurations de chaîne de numérotation d’urgence et de masque de numérotation.
  
 **US-hôpital** : il est nécessaire de ne pas masquer « 450 ». Pour les clients qui ne prennent pas encore en charge plusieurs numéros d’urgence, vous pouvez utiliser les anciennes configurations de chaîne de numérotation d’urgence et de masque de numérotation. Pour les clients qui prennent en charge plusieurs numéros d’urgence, vous pouvez définir un numéro de secours pour « 911 » et « 450 » au lieu de masquer 450.
  
 **Londres** — pour les clients qui ne prennent pas encore en charge plusieurs numéros d’urgence, vous pouvez utiliser les anciennes configurations de chaîne de numérotation d’urgence et de masque de numérotation. Pour les clients qui prennent en charge plusieurs numéros d’urgence, vous pouvez définir un numéro d’urgence pour « 999 » et « 112 » avec des masques pour chacun d’eux.
  
 **Inde** — tous les clients déployés prennent en charge plusieurs numéros d’urgence. En Inde, il vous suffit de configurer plusieurs numéros d’urgence.
  
## <a name="client-support"></a>Prise en charge des clients
<a name="BKMK_Clients"> </a>

Le tableau suivant présente la prise en charge de plusieurs numéros d’urgence pour le client. Microsoft continuera à tester et à lancer la prise en charge de clients supplémentaires. N’hésitez pas à la consulter souvent.

|**Windows**|**Version**|
|:-----|:-----|
|**Démarrer en un clic** <br/> |CC (canal actuel) publié le 10 mai 2016-version 1604 (Build 6868,2062)  <br/> |
||FRDC (première version du canal actuel) publié le 14 juin, 2016-version 1605 (Build 6965,2058)  <br/> |
||DC (canal différé) publié le 11 octobre 2016-version 1605 (Build 6965,2092)  <br/> |
|**MSI** <br/> |Mise à jour du 7 juin-[https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac et iOS** <br/> |**Version** <br/> |
||Skype entreprise Mac client version 16,9  <br/> Client iOS Skype entreprise version 6,16  <br/> |
|**Android** <br/> |**Version** <br/> |
||Skype entreprise client Android version 6,17  <br/> |
|**Lync Phone Edition** <br/> |**Version** <br/> |
|| Aastra 6721ip et Aastra 6725ip Telephones-mise à jour cumulative septembre 2016 (Build 7577,4512)-[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| Téléphones HP 4110 et HP 4120-mise à jour cumulative de septembre 2016 (Build 7577,4512)-[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Téléphones Polycom CX500, Polycom CX600 et Polycom CX3000-mise à jour cumulative septembre 2016 (Build 7577,4512)-[https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
   

