---
title: Planification de plusieurs numéros d'urgence dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Pour savoir comment planifier plusieurs numéros d'urgence dans Skype Entreprise Server 2015, reportez-vous à cette rubrique.
ms.openlocfilehash: f24f895a6d6b0fd5095ef0e03f487fcdf8a98dca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server-2015"></a>Planification de plusieurs numéros d'urgence dans Skype Entreprise 2015
 
Pour savoir comment planifier plusieurs numéros d'urgence dans Skype Entreprise Server 2015, reportez-vous à cette rubrique.
  
Skype pour Business Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Plusieurs numéros d’urgence sont une nouvelle fonctionnalité introduite dans le 2016 juin mise à jour Cumulative. Tandis que les États-Unis disposent d'un seul numéro d'appel d'urgence (911), de nombreux pays/régions prennent en charge plusieurs numéros d'urgence. Au Royaume-Uni, par exemple, prend en charge à la fois 999, le numéro d’urgence spécifique au Royaume-Uni et 112, le numéro d’urgence de l’Union européenne. 
  
Cette fonctionnalité est également utile pour les organismes de soins de santé aux États-Unis qui souhaitent une prise en charge de l'itinérance pour différents numéros d'urgence de code bleu.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Numéros d'urgence multiples et stratégies d'emplacement

Pour configurer un appel d'urgence, créez des stratégies d'emplacement qui définissent le mode d'implémentation de l'appel d'urgence. La stratégie d’emplacement vous permet de définir le numéro constitue un appel d’urgence, par exemple, 911 aux États-Unis ; 999 et 112 au Royaume-Uni. La stratégie d'emplacement détermine si un utilisateur est autorisé à passer des appels d'urgence et, si tel est le cas, définit le comportement de l'appel d'urgence. Vous pouvez également définir si la sécurité de l’entreprise doit être automatiquement notifiée, ainsi que la procédure de routage de l'appel.
  
Pour plus d’informations sur la définition et la modification d’une stratégie d’emplacement, voir [planifier des stratégies d’emplacement pour Skype pour Business Server 2015](location-policies.md) et [créer des stratégies d’emplacement dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/create-location-policies.md). Ces rubriques décrivent les concepts sur les stratégies de l’emplacement ; Toutefois, vous devez suivre les instructions de [configurer plusieurs numéros d’urgence dans Skype pour entreprise 2015](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) pour configurer plusieurs numéros d’urgence.
  
Lors de la planification de numéros d'urgence multiples, tenez compte des points suivants :
  
- Avec le 2016 juin mise à jour Cumulative, vous pouvez définir jusqu'à 5 numéros d’urgence pour une stratégie d’emplacement donné. Avec le 2016 novembre mise à jour Cumulative, ce nombre s’élève à 100.
    
    > [!NOTE]
    > Si vous n'avez pas encore mis à niveau vers le 2016 novembre mise à jour Cumulative, consultez [mises à jour Skype pour Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Pour chaque numéro d’urgence, vous pouvez spécifier zéro, un ou plusieurs masques à distance en cas d’urgence, qui sont uniques à une stratégie d’emplacement donné.
    
    Un masque d’accès est un nombre que vous souhaitez traduire dans la valeur de la valeur du nombre à distance en cas d’urgence, lorsqu’il est composé. Par exemple, supposons que vous entrez une valeur de 212 dans ce champ et le champ de numéro d’accès à distance en cas d’urgence a une valeur de 911. Lorsqu’un utilisateur connecte à 212, le numéro sera traduit (911). Cela permet à d’autres numéros d’urgence à composer et toujours l’appel de contacter les services d’urgence (par exemple, si une personne d’un pays ou une région avec un autre numéro d’urgence tente de composer que pays ou région numérique de la plutôt que le numéro de la pays ou région dans que se trouvent actuellement). Vous pouvez définir plusieurs masques d’accès d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212 ; 414. La limite de chaîne pour un masque d’accès est de 100 caractères. Chaque caractère doit être un chiffre de 0 à 9.
    
- Chaque stratégie d'emplacement dispose d'une utilisation PSTN (réseau téléphonique commuté) unique qui permet de déterminer l'itinéraire de communications vocales utilisé pour router les appels d'urgence de clients à l'aide de cette stratégie. L'utilisation peut avoir un seul itinéraire par numéro d'urgence.
    
- Si les paramètres EmergencyNumbers et DialString sont définis dans une stratégie d'emplacement et que le client prend en charge plusieurs numéros d'urgence, le numéro d'urgence sera prioritaire. Si le client ne prend pas en charge plusieurs numéros d'urgence, la chaîne de numérotation d'urgence sera utilisée.
    
- Pour plus d’informations sur le Skype pour les entreprises et Lync clients prennent en charge la réception de plusieurs numéros d’urgence, composer les masques et les utilisations de réseau téléphonique public commuté, consultez [prise en charge de Client](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Vous ne pouvez pas configurer plusieurs numéros d’urgence à l’aide de la Skype pour panneau de Business. Pour configurer plusieurs numéros d’urgence, vous devez utiliser PowerShell. 
  
Avant de configurer plusieurs numéros d'urgence, tenez compte des points suivants :
  
- Pour configurer plusieurs numéros d’urgence, vous devez utiliser l’applet de commande New-CsEmergencyNumber, et vous devez définir les stratégies d’emplacement qui prennent en charge plus d’un numéro d’urgence en spécifiant le paramètre EmergencyNumbers avec le [Nouveau-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) et Applets de commande [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- 	Si vous avez déjà défini des numéros en utilisant l'applet de commande Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask, les valeurs spécifiées avec le paramètre EmergencyNumbers l'emporteront sur les anciennes valeurs. C’est à dire que les valeurs des paramètres EmergencyDialString et EmergencyDialMask seront ignorées.
    
- Si vous avez des numéros existants définis à l’aide de la CsLocationPolicy de l’ensemble ou l’applet de commande New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask, *et vous ne configurez pas de nouveaux numéros d’urgence* , les numéros existants continueront à être utilisé.
    
- Pour que la fonctionnalité de plusieurs numéros d'urgence fonctionne, les versions clients que vous exécutez doivent pouvoir prendre en charge la nouvelle fonctionnalité. Les anciens clients continueront d’utiliser les anciennes valeurs spécifiées par les applets de commande Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask. 
    
- Si les utilisateurs composent un numéro qui correspond à la chaine de numérotation, aucun masque de numéro n’est nécessaire. Par exemple, si le numéro composé par un utilisateur est le 911, la chaîne de numérotation est alors 911 et aucun masque n’est nécessaire. 
    
Pour plus d’informations sur la configuration de plusieurs numéros d’urgence, voir [configuration d’urgence plusieurs numéros dans Skype pour entreprise 2015](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
Le tableau suivant présente des exemples de stratégies d'emplacement (pour les besoins de l'exemple, tous les attributs ne sont pas indiqués) :
  

|**Nom de stratégie d’emplacement**|**E911 activé**|**Chaîne de connexion en cas d’urgence**|**Masque d’accès à distance**|**Numéros d’urgence**|**Utilisation PSTN**|**Emplacement requis**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis  <br/> |Oui  <br/> |911  <br/> | 112 ; 999 <br/> ||Service d'urgence USA  <br/> |Oui  <br/> |
|Hôpital USA  <br/> |Oui  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Oui  <br/> |
|Londres  <br/> |Oui  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911, 117, 118  <br/> |Service d'urgence RU  <br/> |Non  <br/> |
|Inde  <br/> |Oui  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Non  <br/> |
   
 **États-Unis** — n’est pas obligatoire pour plusieurs numéros d’urgence. Aux États-Unis, vous utilisez les anciennes configurations de chaîne de numérotation d’urgence et masque d’accès à distance.
  
 **Hôpital-aux États-Unis** , il existe une obligation de ne pas masquer « 450 ». Pour les clients qui ne prennent pas encore en charge plusieurs numéros d’urgence, vous pouvez utiliser les configurations de chaîne de connexion en cas d’urgence et masque d’accès anciennes. Pour les clients qui prennent en charge de plusieurs numéros d’urgence, vous pouvez définir un nombre d’urgence « 911 » et « 450 » au lieu de masquage 450.
  
 **Londres** , pour les clients qui ne prennent pas encore en charge plusieurs numéros d’urgence, vous pouvez utiliser les configurations de chaîne de connexion en cas d’urgence et masque d’accès anciennes. Pour les clients qui prennent en charge de plusieurs numéros d’urgence, vous pouvez définir un numéro d’urgence pour « 999 » et « 112 » avec des masques pour chacun.
  
 **L’Inde** , tous les clients déployés prend en charge plusieurs numéros d’urgence. En Inde, vous devez uniquement configurer plusieurs numéros d’urgence.
  
## <a name="client-support"></a>Prise en charge des clients
<a name="BKMK_Clients"> </a>

Le tableau suivant indique la prise en charge des clients pour plusieurs numéros d'urgence. Microsoft continuera à tester et à publier la prise en charge de clients supplémentaires. Veuillez consulter cette page régulièrement.

|**Windows**|**Version**|
|:-----|:-----|
|**Démarrer en un clic** <br/> |CC (canal actuel) publiée le 10 mai 2016 - 1604 de Version (Build 6868.2062)  <br/> |
||Première version du canal actuel (FRDC) publiée le mardi 14 juin 2016 - Version 1605 (Build 6965.2058)  <br/> |
||Canal différé (DC) publié le 11 octobre 2016 - Version 1605 (Build 6965.2092)  <br/> |
|**MSI** <br/> |Mettre à jour le 7 juin-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac et iOS** <br/> |**Version** <br/> |
||Skype pour entreprise Mac version de client annuel 16,9  <br/> Skype pour entreprise iOS version 6.16 du client  <br/> |
|**Android** <br/> |**Version** <br/> |
||Skype pour Android Business version de client 6.17  <br/> |
|**Lync Phone Edition** <br/> |**Version** <br/> |
|| 6721ip de Aastra et de téléphones de 6725ip de Aastra - 2016 de septembre cumulative mise à jour (Build 7577.4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| Téléphones 4110 de HP et HP 4120 - septembre 2016 mise à jour cumulative (Build 7577.4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Téléphones Polycom CX500, CX600 de Polycom et Polycom CX3000 - septembre 2016 mise à jour cumulative (Build 7577.4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

