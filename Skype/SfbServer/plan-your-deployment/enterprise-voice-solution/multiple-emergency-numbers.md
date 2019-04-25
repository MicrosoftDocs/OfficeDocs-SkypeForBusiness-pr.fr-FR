---
title: Planifier plusieurs numéros d’urgence dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Lisez cette rubrique pour savoir comment planifier plusieurs numéros d’urgence dans Skype pour Business Server.
ms.openlocfilehash: e3ecbc039dac510a1ebc5eb989773c1f32c3b6ac
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214158"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planifier plusieurs numéros d’urgence dans Skype pour Business Server
 
Lisez cette rubrique pour savoir comment planifier plusieurs numéros d’urgence dans Skype pour Business Server.
  
Skype pour Business Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Plusieurs numéros d’urgence sont une nouveauté dans le 2016 juin mise à jour Cumulative. Tandis que les États-Unis disposent d'un seul numéro d'appel d'urgence (911), de nombreux pays/régions prennent en charge plusieurs numéros d'urgence. Au Royaume-Uni, par exemple, prend en charge à la fois 999, le numéro d’urgence spécifique au Royaume-Uni et 112, le numéro d’urgence pour l’Union européenne. 
  
Cette fonctionnalité est également utile pour les organismes de soins de santé aux États-Unis qui souhaitent une prise en charge de l'itinérance pour différents numéros d'urgence de code bleu.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Numéros d'urgence multiples et stratégies d'emplacement

Pour configurer un appel d'urgence, créez des stratégies d'emplacement qui définissent le mode d'implémentation de l'appel d'urgence. La stratégie d’emplacement vous permet de définir le numéro constitue un appel d’urgence — par exemple, 911 aux États-Unis ; 999 et 112 au Royaume-Uni. La stratégie d'emplacement détermine si un utilisateur est autorisé à passer des appels d'urgence et, si tel est le cas, définit le comportement de l'appel d'urgence. Vous pouvez également définir si la sécurité de l’entreprise doit être automatiquement notifiée, ainsi que la procédure de routage de l'appel.
  
Pour plus d’informations sur la définition et la modification d’une stratégie d’emplacement, voir [planifier des stratégies d’emplacement pour Skype pour Business Server](location-policies.md) et les [stratégies d’emplacement créer Skype pour Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). Les rubriques suivantes décrivent les concepts sur les stratégies d’emplacement ; Toutefois, vous devez suivre les instructions de [configurer plusieurs numéros d’urgence dans Skype pour les entreprises](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) pour configurer plusieurs numéros d’urgence.
  
Lors de la planification de numéros d'urgence multiples, tenez compte des points suivants :
  
- Avec la 2016 juin mise à jour Cumulative, vous pouvez définir jusqu'à 5 chiffres en cas d’urgence pour une stratégie d’emplacement donné. Avec la 2016 novembre mise à jour Cumulative, ce numéro augmente à 100.
    
    > [!NOTE]
    > Si vous n'avez pas encore mis à niveau vers la 2016 novembre mise à jour Cumulative, consultez [mises à jour Skype pour Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Pour chaque numéro d’urgence, vous pouvez spécifier zéro ou plusieurs masques de numérotation d’urgence, qui sont uniques à une stratégie d’emplacement donné.
    
    Un masque de numérotation est un numéro que vous souhaitez traduire la valeur de la valeur numérique de numérotation d’urgence lorsqu’il est composé. Par exemple, supposons que vous entrez une valeur de 212 dans ce champ et le champ de numéro de numérotation d’urgence a la valeur 911. Lorsqu’un utilisateur connecte 212, le numéro sera traduit en 911. Ainsi, pour les numéros d’urgence substitution être composé tout en conservant l’appel joindre les services d’urgence (par exemple, si une personne de votre pays ou région avec un autre numéro d’urgence tente de numérotation que le pays ou la région s numérique plutôt que le numéro de la pays ou région dans que se trouvent actuellement). Vous pouvez définir plusieurs masques de numérotation d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212 ; 414. La limite de chaîne pour un masque de numérotation est de 100 caractères. Chaque caractère doit être un chiffre de 0 à 9.
    
- Chaque stratégie d'emplacement dispose d'une utilisation PSTN (réseau téléphonique commuté) unique qui permet de déterminer l'itinéraire de communications vocales utilisé pour router les appels d'urgence de clients à l'aide de cette stratégie. L'utilisation peut avoir un seul itinéraire par numéro d'urgence.
    
- Si les paramètres EmergencyNumbers et DialString sont définis dans une stratégie d'emplacement et que le client prend en charge plusieurs numéros d'urgence, le numéro d'urgence sera prioritaire. Si le client ne prend pas en charge plusieurs numéros d'urgence, la chaîne de numérotation d'urgence sera utilisée.
    
- Pour plus d’informations sur le Skype pour les entreprises et Lync clients prennent en charge la réception de plusieurs numéros d’urgence, les masques et les utilisations du réseau téléphonique commuté de numérotation, voir [Client prend en charge](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Vous ne pouvez pas configurer plusieurs numéros d’urgence à l’aide de la Skype pour Business le panneau de configuration. Pour configurer plusieurs numéros d’urgence, vous devez utiliser PowerShell. 
  
Avant de configurer plusieurs numéros d'urgence, tenez compte des points suivants :
  
- Pour configurer plusieurs numéros d’urgence, vous devez utiliser l’applet de commande New-CsEmergencyNumber, et vous devez définir des stratégies d’emplacement qui prennent en charge plus d’un numéro d’urgence en spécifiant le paramètre EmergencyNumbers avec la [Cmdlet New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) et Applets de commande [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- 	Si vous avez déjà défini des numéros en utilisant l'applet de commande Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask, les valeurs spécifiées avec le paramètre EmergencyNumbers l'emporteront sur les anciennes valeurs. C’est à dire que les valeurs des paramètres EmergencyDialString et EmergencyDialMask seront ignorées.
    
- Si vous avez des numéros existants définis à l’aide de la cmdlet Set-CsLocationPolicy ou applet de commande New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask, *et vous ne configurez pas les nouveaux numéros d’urgence* , les numéros existants continueront à être utilisé.
    
- Pour que la fonctionnalité de plusieurs numéros d'urgence fonctionne, les versions clients que vous exécutez doivent pouvoir prendre en charge la nouvelle fonctionnalité. Les anciens clients continueront d’utiliser les anciennes valeurs spécifiées par les applets de commande Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask. 
    
- Si les utilisateurs composent un numéro qui correspond à la chaine de numérotation, aucun masque de numéro n’est nécessaire. Par exemple, si le numéro composé par un utilisateur est le 911, la chaîne de numérotation est alors 911 et aucun masque n’est nécessaire. 
    
Pour plus d’informations sur la configuration de plusieurs numéros d’urgence, voir [configuration d’urgence plusieurs numéros dans Skype pour les entreprises](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
Le tableau suivant présente des exemples de stratégies d'emplacement (pour les besoins de l'exemple, tous les attributs ne sont pas indiqués) :
  

|**Nom de la stratégie d'emplacement**|**E911 activé**|**Chaîne de numérotation d’urgence**|**Masque d'appel**|**Numéros d’urgence**|**Utilisation PSTN**|**Emplacement requis**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis  <br/> |Oui  <br/> |911  
  <br/> | 112;999 <br/> ||Service d'urgence USA  <br/> |Oui  <br/> |
|Hôpital USA  <br/> |Oui  <br/> |911  
  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Oui  <br/> |
|Londres  <br/> |Oui  <br/> |999  
  <br/> |144  <br/> |999-144  <br/> 112-911 117 ; 118  <br/> |Service d'urgence RU  <br/> |Non  <br/> |
|Inde  <br/> |Oui  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Non  <br/> |
   
 **Aux États-Unis** , il n’est pas nécessaire pour plusieurs numéros d’urgence. Aux États-Unis, vous utilisez les configurations de chaîne de numérotation d’urgence et masque de numérotation anciennes.
  
 **Établissements américains** , il est nécessaire que ne pas masquer « 450 ». Pour les clients qui ne prennent pas encore en charge plusieurs numéros d’urgence, vous pouvez utiliser les configurations de chaîne de numérotation d’urgence et masque de numérotation anciennes. Pour les clients qui prennent en charge plusieurs numéros d’urgence, vous pouvez définir un numéro d’urgence pour « 911 » et « 450 » au lieu de masquage 450.
  
 **Londres** – pour les clients qui ne prennent pas encore en charge plusieurs numéros d’urgence, vous pouvez utiliser les configurations de chaîne de numérotation d’urgence et masque de numérotation anciennes. Pour les clients qui prennent en charge plusieurs numéros d’urgence, vous pouvez définir un numéro d’urgence pour « 999 » et « 112 » avec les masques pour chacun.
  
 **Inde** : tous les clients déployés prennent en charge plusieurs numéros d’urgence. En Inde, il vous suffit de configurer plusieurs numéros d’urgence.
  
## <a name="client-support"></a>Prise en charge des clients
<a name="BKMK_Clients"> </a>

Le tableau suivant indique la prise en charge des clients pour plusieurs numéros d'urgence. Microsoft continuera à tester et à publier la prise en charge de clients supplémentaires. Veuillez consulter cette page régulièrement.

|**Windows**|**Version**|
|:-----|:-----|
|**Démarrer en un clic** <br/> |CC (canal actuel) publiées le 10 mai 2016 - Version 1604 (Build 6868.2062)  <br/> |
||Première version du canal actuel (FRDC) publiée le mardi 14 juin 2016 - Version 1605 (Build 6965.2058)  <br/> |
||Canal différé (DC) publié le 11 octobre 2016 - Version 1605 (Build 6965.2092)  <br/> |
|**MSI** <br/> |Mise à jour 7 juin-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac et iOS** <br/> |**Version** <br/> |
||Skype pour Mac Business annuel 16,9 version du client  <br/> Skype pour iOS Business 6.16 version du client  <br/> |
|**Android** <br/> |**Version** <br/> |
||Skype pour Android Business 6.17 version du client  <br/> |
|**Lync Phone Edition** <br/> |**Version** <br/> |
|| Aastra 6721ip et Aastra 6725ip téléphones - septembre 2016 cumulative update (Build 7577.4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| Téléphones HP 4110 et HP 4120 - septembre 2016 mise à jour cumulative (Build 7577.4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Téléphones Polycom CX500, Polycom CX600 et Polycom CX3000 - septembre 2016 mise à jour cumulative (Build 7577.4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

