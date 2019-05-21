---
title: Prévoir plusieurs numéros d’urgence dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Pour plus d’informations sur la planification de plusieurs numéros d’urgence dans Skype entreprise Server, reportez-vous à la rubrique suivante.
ms.openlocfilehash: 43214e42e4fd998aef673ad8d0fbd57ec2d3b498
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276844"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Prévoir plusieurs numéros d’urgence dans Skype entreprise Server
 
Pour plus d’informations sur la planification de plusieurs numéros d’urgence dans Skype entreprise Server, reportez-vous à la rubrique suivante.
  
Skype entreprise Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Plusieurs numéros d’urgence constituent une nouvelle fonctionnalité introduite dans la mise à jour cumulative 2016 de juin. Tandis que les États-Unis disposent d'un seul numéro d'appel d'urgence (911), de nombreux pays/régions prennent en charge plusieurs numéros d'urgence. Par exemple, le Royaume-Uni prend en charge à la fois 999, le numéro d’urgence propre au Royaume-Uni et 112, le numéro d’urgence de l’Union européenne. 
  
Cette fonctionnalité est également utile pour les organismes de soins de santé aux États-Unis qui souhaitent une prise en charge de l'itinérance pour différents numéros d'urgence de code bleu.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Numéros d'urgence multiples et stratégies d'emplacement

Pour configurer un appel d'urgence, créez des stratégies d'emplacement qui définissent le mode d'implémentation de l'appel d'urgence. Utilisez la stratégie d’emplacement pour définir le numéro constituant un appel d’urgence (par exemple, 911 aux États-Unis). 999 et 112 au Royaume-Uni. La stratégie d'emplacement détermine si un utilisateur est autorisé à passer des appels d'urgence et, si tel est le cas, définit le comportement de l'appel d'urgence. Vous pouvez également définir si la sécurité de l’entreprise doit être automatiquement notifiée, ainsi que la procédure de routage de l'appel.
  
Pour plus d’informations sur la définition et la modification d’une stratégie d’emplacement, reportez-vous à la rubrique [planification de stratégies d’emplacement pour Skype entreprise Server](location-policies.md) et [création de stratégies d’emplacement dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). Les rubriques suivantes décrivent les concepts relatifs aux stratégies d’emplacement. Toutefois, vous devez suivre les instructions de la procédure de [configuration de plusieurs numéros d’urgence dans Skype entreprise](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) pour configurer plusieurs numéros d’urgence.
  
Lors de la planification de numéros d'urgence multiples, tenez compte des points suivants :
  
- Avec la mise à jour cumulative 2016 de juin, vous pouvez définir jusqu’à 5 numéros d’urgence pour une stratégie d’emplacement donnée. Avec la mise à jour cumulative 2016 de novembre, ce numéro augmente à 100.
    
    > [!NOTE]
    > Si vous n’avez pas encore effectué la mise à jour vers la version cumulative 2016 de novembre, reportez-vous à la rubrique [mises à jour de Skype entreprise Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Pour chaque numéro de secours, vous pouvez spécifier zéro ou plusieurs masques de numérotation d’urgence, qui sont propres à une stratégie d’emplacement donnée.
    
    Un masque de numérotation est un numéro que vous souhaitez traduire en valeur de la valeur numéro de téléphone d’urgence lors de la numérotation. Par exemple, supposons que vous entriez une valeur de 212 dans ce champ et que le champ numéro de téléphone de secours ait la valeur 911. Lorsqu’un utilisateur compose 212, le numéro est converti en 911. Cela permet d’appeler d’autres numéros d’urgence et de toujours avoir accès aux services d’urgence (par exemple, si un membre d’un pays ou d’une région dont le numéro de téléphone est différent pour composer le numéro de votre pays ou de votre région, et non le numéro de la pays ou région dans lequel ils se trouvent actuellement). Vous pouvez définir plusieurs masques de numérotation d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212; 414. La limite de chaîne d’un masque de numérotation est de 100 caractères. Chaque caractère doit être un chiffre compris entre 0 et 9.
    
- Chaque stratégie d'emplacement dispose d'une utilisation PSTN (réseau téléphonique commuté) unique qui permet de déterminer l'itinéraire de communications vocales utilisé pour router les appels d'urgence de clients à l'aide de cette stratégie. L'utilisation peut avoir un seul itinéraire par numéro d'urgence.
    
- Si les paramètres EmergencyNumbers et DialString sont définis dans une stratégie d'emplacement et que le client prend en charge plusieurs numéros d'urgence, le numéro d'urgence sera prioritaire. Si le client ne prend pas en charge plusieurs numéros d'urgence, la chaîne de numérotation d'urgence sera utilisée.
    
- Pour plus d’informations sur les clients Skype entreprise et Lync prenant en charge la réception de plusieurs numéros d’urgence, des masques de numérotation et des utilisations du réseau téléphonique commuté (PSTN), voir [prise en charge du client](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Vous ne pouvez pas configurer plusieurs numéros d’urgence à l’aide du panneau de configuration Skype pour les entreprises. Pour configurer plusieurs numéros d’urgence, vous devez utiliser PowerShell. 
  
Avant de configurer plusieurs numéros d'urgence, tenez compte des points suivants :
  
- Pour configurer plusieurs numéros d’urgence, vous devez utiliser l’applet de nouvelle applet de nouveau-CsEmergencyNumber et définir des stratégies d’emplacement prenant en charge plusieurs numéros d’urgence en spécifiant le paramètre EmergencyNumbers avec le [nouveau-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) et Cmdlet [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- 	Si vous avez déjà défini des numéros en utilisant l'applet de commande Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask, les valeurs spécifiées avec le paramètre EmergencyNumbers l'emporteront sur les anciennes valeurs. C’est à dire que les valeurs des paramètres EmergencyDialString et EmergencyDialMask seront ignorées.
    
- Si vous avez des numéros existants définis à l’aide de l’applet de nouvelle cmdlet Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask *et que vous ne configurez pas de nouveaux numéros d’urgence* , les numéros existants continuent à être utilisée.
    
- Pour que la fonctionnalité de plusieurs numéros d'urgence fonctionne, les versions clients que vous exécutez doivent pouvoir prendre en charge la nouvelle fonctionnalité. Les anciens clients continueront d’utiliser les anciennes valeurs spécifiées par les applets de commande Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask. 
    
- Si les utilisateurs composent un numéro qui correspond à la chaine de numérotation, aucun masque de numéro n’est nécessaire. Par exemple, si le numéro composé par un utilisateur est le 911, la chaîne de numérotation est alors 911 et aucun masque n’est nécessaire. 
    
Pour plus d’informations sur la configuration de plusieurs numéros d’urgence, reportez-vous à la rubrique [configuration de plusieurs numéros d’urgence dans Skype entreprise](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
Le tableau suivant présente des exemples de stratégies d'emplacement (pour les besoins de l'exemple, tous les attributs ne sont pas indiqués) :
  

|**Nom de la stratégie d'emplacement**|**E911 activé**|**Chaîne de numérotation d’urgence**|**Masque d'appel**|**Numéros d’urgence**|**Utilisation PSTN**|**Emplacement requis**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis  <br/> |Oui  <br/> |911  
  <br/> | 112;999 <br/> ||Service d'urgence USA  <br/> |Oui  <br/> |
|Hôpital USA  <br/> |Oui  <br/> |911  
  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Oui  <br/> |
|Londres  <br/> |Oui  <br/> |999  
  <br/> |144  <br/> |999-144  <br/> 112-911; 117; 118  <br/> |Service d'urgence RU  <br/> |Non  <br/> |
|Inde  <br/> |Oui  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Non  <br/> |
   
 **États-Unis** : il n’est pas nécessaire de disposer de multiples numéros d’urgence. Aux États-Unis, vous utilisez l’ancien numéro de téléphone d’urgence et les configurations de masque de numérotation.
  
 **États-Unis-hôpital** : il n’est pas nécessaire de masquer «450». Pour les clients qui ne prennent pas encore en charge plusieurs numéros d’urgence, vous pouvez utiliser l’ancien numéro de téléphone d’urgence et les configurations de masque de numérotation. Pour les clients qui prennent en charge plusieurs numéros d’urgence, vous pouvez définir un numéro d’urgence pour les "911" et "450" au lieu de masquer 450.
  
 **Londres** : pour les clients qui ne prennent pas encore en charge plusieurs numéros d’urgence, vous pouvez utiliser l’ancien numéro de téléphone d’urgence et les configurations de masque de numérotation. Pour les clients qui prennent en charge plusieurs numéros d’urgence, vous pouvez définir un numéro d’urgence pour les "999" et "112" avec des masques pour chacun.
  
 **Inde** : tous les clients déployés prennent en charge plusieurs numéros d’urgence. En Inde, il vous suffit de configurer plusieurs numéros d’urgence.
  
## <a name="client-support"></a>Prise en charge des clients
<a name="BKMK_Clients"> </a>

Le tableau suivant indique la prise en charge des clients pour plusieurs numéros d'urgence. Microsoft continuera à tester et à publier la prise en charge de clients supplémentaires. Veuillez consulter cette page régulièrement.

|**Windows**|**Version**|
|:-----|:-----|
|**Démarrer en un clic** <br/> |CC (canal actuel) publiée le 10 2016-version 1604 (Build 6868,2062)  <br/> |
||Première version du canal actuel (FRDC) publiée le mardi 14 juin 2016 - Version 1605 (Build 6965.2058)  <br/> |
||Canal différé (DC) publié le 11 octobre 2016 - Version 1605 (Build 6965.2092)  <br/> |
|**MSI** <br/> |Mise à jour du 7 juin-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac et iOS** <br/> |**Version** <br/> |
||Client Mac Skype entreprise version 16,9  <br/> Client iOS Skype entreprise version 6,16  <br/> |
|**Android** <br/> |**Version** <br/> |
||Client Android Skype entreprise version 6,17  <br/> |
|**Lync Phone Edition** <br/> |**Version** <br/> |
|| Aastra 6721ip and Aastra 6725ip de téléphone-mise à jour cumulative 2016 de septembre (Build 7577,4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| Téléphones HP 4110 et HP 4120: mise à jour cumulative de septembre 2016 (Build 7577,4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Polycom CX500, Polycom CX600 et Polycom CX3000 de téléphone-mise à jour cumulative 2016 de septembre (Build 7577,4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

