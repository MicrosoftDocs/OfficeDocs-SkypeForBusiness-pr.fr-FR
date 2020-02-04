---
title: 'Lync Server 2013 : exécution et surveillance de sauvegardes'
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
ms.openlocfilehash: 3181a266e5792d190186e9f09b2cab5852156cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Exécution et analyse des sauvegardes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-15_

Les priorités de votre entreprise doivent conduire à la spécification des exigences de sauvegarde et de restauration pour votre organisation. La sauvegarde des serveurs et des données est la première ligne de défense de la planification d’un sinistre.

Les ordinateurs qui exécutent les services ou rôles serveur Lync Server 2013 doivent avoir une copie de la topologie actuelle, des paramètres de configuration actuels et des stratégies actuelles pour pouvoir fonctionner dans leur rôle désigné. Lync Server est tenu de s’assurer que ces informations sont transmises à chaque ordinateur qui en a besoin.

Les applets **de suivi Export-CsConfiguration** et **Import-CsConfiguration** sont utilisés pour sauvegarder et restaurer votre topologie de serveur Lync, vos paramètres de configuration et vos stratégies lors d’une mise à niveau centralisée du magasin. Les applets **de passe Export-CsConfiguration** vous permettent d’exporter des données vers un. Fichier ZIP. Vous pouvez ensuite utiliser l’applet de cmdlet **Import-CsConfiguration** pour la lire. ZIP et restaurez la topologie, les paramètres de configuration et les stratégies dans le centre de gestion central. Après cela, les services de réplication de Lync Server répliquent les informations restaurées sur d’autres ordinateurs exécutant des services serveur Lync.

La possibilité d’exporter et d’importer des données de configuration est également utilisée lors de la configuration initiale d’ordinateurs situés dans votre réseau de périmètre (par exemple, serveurs de périphérie). Lorsque vous configurez un ordinateur dans le réseau de périmètre, vous devez d’abord effectuer une réplication manuelle à l’aide des applets de commande CsConfiguration : vous devez exporter les données de configuration en utilisant **Export-CsConfiguration** , puis copier le. ZIP vers l’ordinateur dans le réseau de périmètre. Après cela, vous pouvez utiliser **Import-CsConfiguration** et le paramètre LocalStore pour importer les données. Vous ne devez effectuer cette opération qu’une seule fois. Après cela, la réplication sera exécutée automatiquement.

Qui peut exécuter cette applet de commande : par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande **Export-CsConfiguration** localement : RTCUniversalServerAdmins. Pour renvoyer la liste de tous les rôles RBAC, cette applet de commande est affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell :

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

Toutes les bases de données principales SQL 2012 doivent être sauvegardées conformément aux [meilleures pratiques SQL](http://go.microsoft.com/fwlink/p/?linkid=290716).

Le test régulier du plan de reprise après sinistre pour votre infrastructure Lync Server 2013 doit être effectué dans un environnement de laboratoire qui imite l’environnement de production aussi fidèlement que possible. Pour plus d’informations sur les tests de récupération d’urgence, reportez-vous aux tâches mensuelles.

Notez que la fréquence de sauvegarde peut être ajustée en fonction de vos objectifs en matière de points de restauration et de points de récupération. Nous vous conseillons de prendre des instantanés périodiques et périodiques tout au long de la journée. En règle générale, vous devez effectuer des sauvegardes complètes toutes les 24 heures.

<div>

## <a name="see-also"></a>Voir aussi


[Importation-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[Meilleures pratiques SQL](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

