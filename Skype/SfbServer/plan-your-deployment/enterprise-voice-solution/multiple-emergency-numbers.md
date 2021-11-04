---
title: Planifier plusieurs numéros d’urgence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Lisez cette rubrique pour découvrir comment planifier plusieurs numéros d’urgence dans Skype Entreprise Server.
ms.openlocfilehash: 8e4761b22295d71c33af414e2a92dac7bf1210d6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741961"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planifier plusieurs numéros d’urgence dans Skype Entreprise Server
 
Lisez cette rubrique pour découvrir comment planifier plusieurs numéros d’urgence dans Skype Entreprise Server.
  
Skype Entreprise Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Plusieurs numéros d’urgence sont une nouvelle fonctionnalité introduite dans la mise à jour cumulative de juin 2016. Alors que les États-Unis disposent d’un seul numéro d’urgence( 911), de nombreux pays en assurent plusieurs. Le Royaume-Uni, par exemple, prend en charge le 999, le numéro d’urgence spécifique au Royaume-Uni, et le 112, le numéro d’urgence pour l’Union européenne. 
  
Cette fonctionnalité est également utile pour les fournisseurs de soins de santé aux États-Unis qui souhaitent prendre en charge l’itinérance pour plusieurs numéros d’urgence en bleu code.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Plusieurs numéros d’urgence et stratégies d’emplacement

Vous configurez les appels d’urgence en créant des stratégies d’emplacement qui définissent la façon dont les appels d’urgence seront implémentés. Vous utilisez la stratégie d’emplacement pour définir le numéro qui constitue un appel d’urgence, par exemple, 911 aux États-Unis ; 999 et 112 au Royaume-Uni. La stratégie d’emplacement détermine si un utilisateur est activé pour les appels d’urgence et, si tel est le cas, le comportement d’un appel d’urgence. Vous pouvez également définir si la sécurité d’entreprise doit être avertie automatiquement et comment l’appel doit être acheminé.
  
Pour plus d’informations sur la définition et la modification d’une stratégie d’emplacement, voir [Plan location policies for Skype Entreprise Server](location-policies.md) and Create location policies in [Skype Entreprise Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). Ces rubriques décrivent les concepts liés aux stratégies d’emplacement . Toutefois, vous devez suivre les instructions de la procédure [Configure multiple emergency numbers in Skype Entreprise](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) to configure multiple emergency numbers.
  
Lorsque vous planifiez plusieurs numéros d’urgence, gardez les points suivants à l’esprit :
  
- Avec la mise à jour cumulative de juin 2016, vous pouvez définir jusqu’à 5 numéros d’urgence pour une stratégie d’emplacement donnée. Avec la mise à jour cumulative de novembre 2016, ce nombre augmente jusqu’à 100.
    
    > [!NOTE]
    > Si vous n’avez pas encore mis à niveau vers la mise à jour cumulative de novembre 2016, voir Mises à jour [Skype Entreprise Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Pour chaque numéro d’urgence, vous pouvez spécifier zéro ou plusieurs masques de numérotation d’urgence, qui sont propres à une stratégie d’emplacement donnée.
    
    Un masque de numérotation est un numéro que vous souhaitez traduire en valeur de numéro d’urgence lorsqu’il est composé. Par exemple, supposons que vous entrez la valeur 212 dans ce champ et que le champ numéro de numéro d’urgence a la valeur 911. Lorsqu’un utilisateur compose le 212, le numéro est converti en 911. Cela permet de composer d’autres numéros d’urgence tout en permettant à l’appel d’accéder aux services d’urgence (par exemple, si une personne d’un pays ou d’une région dont le numéro d’urgence est différent tente de composer le numéro de ce pays ou de cette région plutôt que le numéro du pays ou de la région où elle se trouve actuellement). Vous pouvez définir plusieurs masques d’appel d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212;414. La limite de chaîne pour un masque de numérotation est de 100 caractères. Chaque caractère doit être un chiffre compris entre 0 et 9.
    
- Chaque stratégie d’emplacement a une utilisation PSTN (réseau téléphonique commuté) unique qui permet de déterminer l’itinéraire des communications vocales utilisé pour router les appels d’urgence des clients à l’aide de cette stratégie. L’utilisation peut avoir un itinéraire unique par numéro d’urgence.
    
- Si les paramètres EmergencyNumbers et DialString sont définis dans une stratégie d’emplacement et que le client prend en charge plusieurs numéros d’urgence, le numéro d’urgence est prioritaire. Si le client ne prend pas en charge plusieurs numéros d’urgence, la chaîne de numérotation d’urgence est utilisée.
    
- Pour plus d’informations sur les clients Skype Entreprise et Lync qui peuvent recevoir plusieurs numéros d’urgence, masques de numérotation et utilisations du réseau téléphonique commuté (PSTN), voir Prise en charge du [client.](multiple-emergency-numbers.md#BKMK_Clients)
    
> [!NOTE]
> Vous ne pouvez pas configurer plusieurs numéros d’urgence à l’aide Skype Entreprise panneau de configuration. Vous devez utiliser PowerShell pour configurer plusieurs numéros d’urgence. 
  
Avant de configurer plusieurs numéros d’urgence, gardez les points suivants à l’esprit :
  
- Pour configurer plusieurs numéros d’urgence, vous devez utiliser l’cmdlet New-CsEmergencyNumber et définir des stratégies d’emplacement qui prendre en charge plusieurs numéros d’urgence en spécifiant le paramètre EmergencyNumbers avec les cmdlets [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) et [Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)
    
- Si vous avez des numéros existants définis à l’aide de la cmdlet Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask, les valeurs spécifiées avec le paramètre EmergencyNumbers prévalent sur les anciennes valeurs. Autrement dit, les valeurs des paramètres EmergencyDialString et EmergencyDialMask seront ignorées.
    
- Si vous avez des numéros existants définis à l’aide de la cmdlet Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask  *et*  que vous ne configurez pas de nouveaux numéros d’urgence, les numéros existants continueront d’être utilisés.
    
- Pour que la fonctionnalité de numéros d’urgence multiples fonctionne, les versions des clients que vous exécutez doivent être en mesure de prendre en charge la nouvelle fonctionnalité. Les clients plus anciens continueront d’utiliser les anciennes valeurs spécifiées par les cmdlets Set-CsLocationPolicy ou New-CsLocationPolicy avec les paramètres EmergencyDialString et EmergencyDialMask. 
    
- Si les utilisateurs composeront un numéro qui correspond à la chaîne de numérotation, aucun masque de numérotation n’est requis. Par exemple, si le numéro composé par un utilisateur est 911, la chaîne de numérotation est 911 et aucun masque n’est requis. 
    
Pour plus d’informations sur la configuration de plusieurs numéros d’urgence, voir Configurer plusieurs numéros [d’urgence dans Skype Entreprise](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
Le tableau suivant présente des exemples de stratégies d’emplacement (pour les besoins de l’exemple, tous les attributs ne sont pas affichés) :
  

|**Nom de la stratégie d’emplacement**|**E911 activé**|**Chaîne de numérotation d’urgence**|**Masque de numérotation**|**Numéros d’urgence**|**Utilisation PSTN**|**Emplacement requis**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis  <br/> |Oui  <br/> |911  <br/> | 112;999 <br/> ||USEmergency  <br/> |Oui  <br/> |
|US-Hospital  <br/> |Oui  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Oui  <br/> |
|Londres  <br/> |Oui  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911;117;118  <br/> |GBEmergency  <br/> |Non  <br/> |
|Inde  <br/> |Oui  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Non  <br/> |
   
 **États-Unis** : il n’est pas nécessaire d’avoir plusieurs numéros d’urgence. Aux États-Unis, vous utilisez les anciennes configurations de chaîne de numérotation d’urgence et de masque de numérotation.
  
 **US-Hôpital** — Il est nécessaire de ne pas masquer « 450 ». Pour les clients qui ne peuvent pas encore prendre en charge plusieurs numéros d’urgence, vous pouvez utiliser les anciennes configurations de chaîne de numérotation d’urgence et de masque de numérotation. Pour les clients qui supportent plusieurs numéros d’urgence, vous pouvez définir un numéro d’urgence pour « 911 » et « 450 » au lieu de masquer 450.
  
 **Londres —** Pour les clients qui ne peuvent pas encore prendre en charge plusieurs numéros d’urgence, vous pouvez utiliser les anciennes configurations de chaîne de numérotation d’urgence et de masque de numérotation. Pour les clients qui supportent plusieurs numéros d’urgence, vous pouvez définir un numéro d’urgence pour « 999 » et « 112 » avec des masques pour chacun d’eux.
  
 **Inde** — Tous les clients déployés supportent plusieurs numéros d’urgence. En Inde, vous devez uniquement configurer plusieurs numéros d’urgence.
  
## <a name="client-support"></a>Prise en charge des clients
<a name="BKMK_Clients"> </a>

Le tableau suivant indique la prise en charge de plusieurs numéros d’urgence par le client. Microsoft continuera à tester et publier la prise en charge pour d’autres clients. N’hésitez pas à la consulter souvent.

|**Fenêtres**|**Version**|
|:-----|:-----|
|**Démarrer en un clic** <br/> |Cc (canal actuel) publié le 10 mai 2016 - Version 1604 (build 6868.2062)  <br/> |
||FRDC (First Release Current Channel) publiée le 14 juin 2016 - Version 1605 (build 6965.2058)  <br/> |
||DC (Canal différé) publié le 11 octobre 2016 - Version 1605 (build 6965.2092)  <br/> |
|**MSI** <br/> |Mise à jour du 7 juin - [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac et iOS** <br/> |**Version** <br/> |
||Skype Entreprise Client Mac version 16.9  <br/> Skype Entreprise client iOS version 6.16  <br/> |
|**Android** <br/> |**Version** <br/> |
||Skype Entreprise Client Android version 6.17  <br/> |
|**Lync Phone Edition** <br/> |**Version** <br/> |
|| Téléphones Aastra 6721ip et Aastra 6725ip - Mise à jour cumulative de septembre 2016 (build 7577.4512) -[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| Téléphones HP 4110 et HP 4120 - Mise à jour cumulative de septembre 2016 (build 7577.4512) -[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Téléphones Polycom CX500, Polycom CX600 et Polycom CX3000 - Mise à jour cumulative de septembre 2016 (build 7577.4512) - [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
