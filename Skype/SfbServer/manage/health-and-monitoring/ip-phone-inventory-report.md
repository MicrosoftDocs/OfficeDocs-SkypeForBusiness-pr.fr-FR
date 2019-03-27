---
title: Rapport d’inventaire de téléphonie IP dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
description: 'Résumé : Découvrez le rapport d’inventaire téléphone IP dans Skype pour Business Server.'
ms.openlocfilehash: 02c98d9f3a1adbe7adf6810def04fcbffe2de3bd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897572"
---
# <a name="ip-phone-inventory-report-in-skype-for-business-server"></a>Rapport d’inventaire de téléphonie IP dans Skype pour Business Server
 
**Résumé :** Découvrez le rapport d’inventaire téléphone IP dans Skype pour Business Server.
  
Le Rapport d’inventaire de téléphonie IP fournit des informations sur les téléphones IP en cours d’utilisation dans votre organisation. Il offre une liste détaillée des téléphones IP qui ont été utilisées durant la période de rapport spécifiée. Entre autres choses, il permet aux administrateurs de savoir s’il existe des téléphones obsolètes qui doivent être remplacés. Il peut également les alerter quant à la présence de téléphones coûteux rarement utilisés. Ce type d’informations peut être précieux dans le cadre de l’achat de nouveaux téléphones ou de la redistribution des téléphones existants (par exemple, il peut être demandé à un utilisateur qui n’utilise son téléphone coûteux que très rarement de l’échanger avec un autre utilisateur qui utilise le sien beaucoup plus fréquemment).
  
Il convient de noter que ce rapport n’a quelques limitations lorsqu’il s’agit d’être utilisé comme un rapport d’inventaire de la valeur true. Tout d’abord, le rapport de téléphonie IP répertorie simplement tous les téléphones qui a ouvert une session sur Skype pour Business Server pendant la période spécifiée, triés par leur dernière connexion. Si un téléphone vous n'êtes pas connecté au cours de la période spécifiée puis il apparaîtra pas dans le rapport d’inventaire. Qui inclut les téléphones connectés avant la période de temps en route et étaient toujours connectés pendant l’intervalle de temps spécifié. Par exemple, supposons que vous souhaitez examiner les emplacements de téléphone pour juillet 2015. Ainsi, supposons que plusieurs téléphones ouvert une session sur Skype pour Business Server sur 30 juin 2015 et qu’étaient toujours connectés à compter du 1er juillet. Ces téléphones s’affichera pas sur le rapport d’inventaire pour le 1er juillet.
  
Il convient également de noter que le rapport d’inventaire pourrait inclure des téléphones que votre organisation n’utilise plus. Supposez par exemple, que plusieurs téléphones Fabrikam se sont connectés au système le 1er juillet 2015 ; cinq jours plus tard, votre organisation s’est débarrassée de tous ces téléphones Fabrikam et les a remplacés par un modèle Contoso plus récent. Les téléphones Fabrikam apparaîtront tout de même dans le rapport d’inventaire simplement du fait qu’ils se sont connectés au système durant le mois de juillet.
  
En outre, le Rapport d’inventaire de téléphonie IP ne fournit aucun total récapitulatif pour les différents types de téléphones. Par exemple, supposez que vous avez 105 téléphones Polycom CX600. Le rapport ne vous indiquera pas que vous avez 105 de ces téléphones ; au lieu de cela, vous verrez simplement 105 entrées distinctes pour le Polycom Cx600. Le seul moyen de savoir qu’il y a 105 entrées pour le Polycom Cx600 serait de compter chacune de ces entrées manuellement.
  
> [!TIP]
> Vous pourriez également exporter les données et utiliser Microsoft Excel ou Windows PowerShell pour compter les entrées à votre place. 
  
## <a name="accessing-the-ip-phone-inventory-report"></a>Accès au Rapport d’inventaire de téléphonie IP

Le Rapport d’inventaire de téléphonie IP est accessible à partir de la page d’accueil des Rapports de surveillance. Un clic sur la métrique URI utilisateur vous permet d’accéder au Rapport d’activité de l’utilisateur. Un clic sur la métrique Dernière activité pour appel P2P permet d’accéder au Rapport détaillé de session P2P ; un clic sur cette même métrique pour une conférence permet d’accéder au Rapport détaillé de conférence.
  
## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>Utilisation optimale du Rapport d’inventaire de téléphonie IP

Si seules les informations d’utilisation d’un type de téléphone spécifique vous intéressent (par exemple, « Quelle est la fréquence d’utilisation des téléphones Polycom CX600 ? »), vous pouvez obtenir ces informations directement grâce au Rapport d’inventaire de téléphonie IP en filtrant ce type de téléphone spécifique. En revanche, si vous souhaitez obtenir des données de synthèse pour tous vos téléphones (combien de personnes utilisent un Polycom CX600, combien utilisent un LG-Nortel IP8540, et ainsi de suite), vous devrez exporter les données et utiliser une autre application (telle que Windows PowerShell) pour effectuer ce type d’analyse. Supposez, par exemple, que vous exportez les données vers un fichier de valeurs séparées par des virgules (C:\Data\IP_Phone_Inventory_Report.csv). Dans ce cas, vous pourriez utiliser les deux commandes suivantes pour obtenir des données de synthèse pour tous vos téléphones :
  
```
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending
```

Des données semblables à ceci sont renvoyées :
  
<pre>
Count    Name
-----    ----
  267    POLYCOM, CX700
  267    POLYCOM, CX600
  166    POLYCOM, C
   68    Microsoft, CPE
   64    LG-Nortel, IP8540
   59    Aastra, 6725ip
   37    LG-Nortel, IP
   22    POLYCOM, CX3000
   11    Microsoft, CPE_A
    9    POLYCOM, CX500
    7    Aastra, 6721ip
</pre>

De mêmes, ces deux commandes indiquent quels téléphones se sont connectés au système mais n’ont jamais été utilisés pour effectuer un appel (la valeur de la métrique Dernière activité est vierge, ce qui indique l’absence de dernière activité) :
  
```
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones | Where-Object {$_."Last activity" -eq ""}
```

Cette commande renvoie des données semblables aux suivantes pour chaque téléphone qui n’a pas été utilisé :
  
<pre>
Manufacturer     : POLYCOM
Hardware version : CX600
MAC address      : 00-04-F2-00-01-76
User URI         : 422
User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
Last logon time  : 8/30/2010 4:44:48 PM
Last logoff time : 8/30/2010 5:59:07 PM
Last activity    :
</pre>

Le Rapport d’inventaire de téléphonie IP offre un autre avantage : si vous connaissez l’adresse MAC d’un téléphone IP, vous pouvez identifier le dernier utilisateur ayant utilisé ce téléphone en entrant simplement cette adresse dans la zone de texte Adresse MAC. Le Rapport d’inventaire de téléphonie IP indiquera alors (entre autres choses) l’adresse SIP du dernier utilisateur qui s’est connecté avec ce téléphone. En guise d’alternative, vous pouvez entrer l’adresse SIP d’un utilisateur (dans la zone Préfixe d’URI de l’utilisateur) pour dresser la liste de tous les téléphones qui ont été utilisés par cet utilisateur.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, avec le rapport d’inventaire de téléphonie IP il est possible d’afficher uniquement les téléphones fabriqués par une société spécifique ou même une version spécifique de ces téléphones. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les inscriptions sont groupées par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’inventaire de téléphonie IP.
  
**Filtres de rapport d’inventaire de téléphonie IP**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Fabricant** <br/> |Nom de la société ayant fabriqué le téléphone IP. Les valeurs pour ce filtre sont remplies automatiquement pour vous en fonction des téléphones IP actuellement présents dans la base de données.  <br/> |
|**Version du matériel** <br/> |Numéro de version du téléphone IP ; les filtres Fabricant et Version du matériel vous permettent d’identifier de manière unique un type de téléphone particulier. Les valeurs pour ce filtre sont remplies automatiquement pour vous en fonction des téléphones IP actuellement présents dans la base de données.  <br/> |
|**Agent utilisateur** <br/> |Identifiant du logiciel utilisé par le téléphone IP. Les valeurs pour ce filtre sont remplies automatiquement pour vous en fonction des téléphones IP actuellement présents dans la base de données.  <br/> |
|**Adresse MAC** <br/> |Identifiant unique de l’interface réseau sur le téléphone IP. L’adresse MAC (Media Access Control) est généralement affectée lors de la fabrication du téléphone ; elle est codée en dur dans le matériel du périphérique.  <br/> Pour rechercher des enregistrements associés à une adresse MAC spécifique, il suffit d’entrer cette adresse. Par exemple :  <br/> 00-08-5D-16-16-48  <br/> Vous devez entrer l’adresse complète. Une adresse partielle (par exemple, 00-08-5D) ne renvoie aucune donnée.  <br/> |
|**Dernière activité avant les jours** <br/> | Sélectionnez l’une des valeurs suivantes : <br/>  [Tous] <br/>  10 <br/>  20 <br/>  30 <br/> |
|**Heure de la dernière fermeture de session avant les jours** <br/> | Sélectionnez l’une des valeurs suivantes : <br/>  [Tous] <br/>  10 <br/>  20 <br/>  30 <br/> |
|**Préfixe URI de l’utilisateur** <br/> |Adresse SIP de l’utilisateur qui a utilisé le téléphone IP.  <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport d’inventaire de téléphonie IP.
  
**Mesures du rapport d’inventaire de téléphonie IP**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Fabricant** <br/> |Oui  <br/> |Nom de la société ayant fabriqué le téléphone IP.  <br/> |
|**Version du matériel** <br/> |Oui  <br/> |Numéro de version du téléphone IP.  <br/> |
|**Adresse MAC** <br/> |Oui  <br/> |Identifiant unique de l’interface réseau sur le téléphone IP. L’adresse MAC est généralement affectée lors de la fabrication du téléphone ; elle est codée en dur dans le matériel du périphérique.  <br/> |
|**URI utilisateur** <br/> |Oui  <br/> |Adresse SIP de l’utilisateur qui a utilisé le téléphone IP.  <br/> |
|**Agent utilisateur** <br/> |Oui  <br/> |Identifiant du logiciel utilisé par le téléphone IP.  <br/> |
|**Heure de la dernière ouverture de session** <br/> |Oui  <br/> |Date et heure auxquelles le téléphone IP dernière ouverture de session Skype pour Business Server.  <br/> |
|**Heure de la dernière fermeture de session** <br/> |Oui  <br/> |Date et heure auxquelles le téléphone IP dernière fermeture de session de Skype pour Business Server.  <br/> |
|**Dernière activité** <br/> |Oui  <br/> |Date et heure de la dernière utilisation de ce téléphone IP.  <br/> |
   

