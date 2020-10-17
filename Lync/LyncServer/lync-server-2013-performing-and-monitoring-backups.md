---
title: 'Lync Server 2013 : exécution et surveillance des sauvegardes'
description: 'Lync Server 2013 : exécution et surveillance des sauvegardes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb8ce99e850f0918974be08eb10796ef1397225
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557230"
---
# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Exécution et surveillance des sauvegardes dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-15_

Les priorités de votre entreprise doivent conduire la spécification des exigences en matière de sauvegarde et de restauration pour votre organisation. Effectuer des sauvegardes des serveurs et des données est la première ligne de défense de la planification d’un sinistre.

Les ordinateurs qui exécutent des services ou des rôles serveur Lync Server 2013 doivent disposer d’une copie de la topologie actuelle, des paramètres de configuration actuels et des stratégies actuelles pour qu’ils puissent fonctionner dans leur rôle nommé. Lync Server est chargé de s’assurer que ces informations sont transmises à chaque ordinateur qui en a besoin.

Les applets de commande **Export-CsConfiguration** et **Import-CsConfiguration** sont utilisées pour sauvegarder et restaurer votre topologie Lync Server, vos paramètres de configuration et vos stratégies pendant une mise à niveau du magasin central de gestion. Les applets de commande **Export-CsConfiguration** vous permettent d’exporter des données vers un. Fichier ZIP. Vous pouvez ensuite utiliser l’applet de commande **Import-CsConfiguration** pour la lire. ZIP et restaurez la topologie, les paramètres de configuration et les stratégies dans le magasin central de gestion. Ensuite, les services de réplication de Lync Server répliquent les informations restaurées vers les autres ordinateurs qui exécutent les services Lync Server.

La possibilité d’exporter et d’importer des données de configuration est également utilisée lors de la configuration initiale des ordinateurs situés dans votre réseau de périmètre (par exemple, les serveurs Edge). Lors de la configuration d’un ordinateur dans le réseau de périmètre, vous devez d’abord effectuer une réplication manuelle à l’aide des applets de commande CsConfiguration : vous devez exporter les données de configuration à l’aide de **Export-CsConfiguration** , puis copier le. ZIP sur l’ordinateur dans le réseau de périmètre. Ensuite, vous pourrez utiliser l’applet de commande **Import-CsConfiguration** et le paramètre LocalStore pour importer les données. Vous ne devez effectuer cette opération qu’une seule fois. Une fois cette opération effectuée, la réplication se produit automatiquement.

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes qui suivent sont autorisés à exécuter localement l’applet de commande **Export-CsConfiguration** : RTCUniversalServerAdmins. Pour renvoyer la liste de tous les rôles RBAC, cette applet de commande est affectée à (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell :

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

Toutes les bases de données principales SQL 2012 doivent être sauvegardées conformément aux [meilleures pratiques SQL](https://go.microsoft.com/fwlink/p/?linkid=290716).

Le test régulier du plan de récupération d’urgence de votre infrastructure Lync Server 2013 doit être effectué dans un environnement de laboratoire qui imite l’environnement de production aussi étroitement que possible. Pour plus d’informations sur les tests de récupération d’urgence, reportez-vous aux tâches mensuelles.

Notez que la fréquence de sauvegarde peut être ajustée en fonction de vos objectifs de point de restauration et de point de récupération. Il est recommandé de prendre des instantanés périodiques réguliers tout au long de la journée. En règle générale, vous devez effectuer des sauvegardes complètes toutes les 24 heures.

<div>

## <a name="see-also"></a>Voir aussi


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[Meilleures pratiques SQL](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

