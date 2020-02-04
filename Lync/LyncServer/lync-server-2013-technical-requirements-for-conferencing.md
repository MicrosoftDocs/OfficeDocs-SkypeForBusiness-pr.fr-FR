---
title: Configuration technique requise pour les conférences dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a275836b940cfe2c56b184d238bc12c432132e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Configuration technique requise pour les conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-25_

Pour Lync Server 2013, les conférences rendez-vous, les conférences rendez-vous, les conférences par messagerie instantanée et les fonctionnalités de conférences Web toujours exécutées sur des serveurs frontaux.

Cette section détaille les configurations matérielles et logicielles requises pour ces serveurs, ainsi que la colocalisation prise en charge.

La fonction de conférence rendez-vous est une fonctionnalité qui inclut de nombreux composants. Certains composants sont spécifiques aux conférences rendez-vous, et certains sont des composants voix entreprise. Cette section décrit les exigences relatives aux composants spécifiques aux conférences rendez-vous. Pour plus d’informations sur la configuration requise pour les passerelles de réseau téléphonique commuté (RTC) et de réseau téléphonique commuté (RTC), consultez la section [composant serveur de médiation dans Lync server 2013](lync-server-2013-mediation-server-component.md) et les [composants et topologies du serveur de médiation dans Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) dans la documentation de planification.

<div>

## <a name="hardware-requirements"></a>Configuration matérielle requise

Dans la mesure où les conférences Web et les conférences à l’aide de la fonctionnalité de conférence A/V sont colocalisées avec le serveur frontal, la configuration matérielle requise pour le serveur est la même que celle des serveurs frontaux. Pour plus d’informations sur la configuration matérielle requise, voir [plates-formes matérielles pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation relative à la prise en charge. Les composants suivants requis pour les conférences rendez-vous présentent également les mêmes exigences matérielles que les serveurs frontaux :

  - service d’application

  - application Intendant Conférence

  - application d’annonce de conférence

La configuration matérielle requise pour le serveur frontal est la même que celle de nombreux autres rôles de serveur dans Lync Server 2013, comme indiqué dans le tableau suivant.

</div>

<div>

## <a name="software-requirements"></a>Configuration logicielle requise

Dans la mesure où les conférences Web et les conférences A/V sont colocalisées avec le serveur frontal, la configuration logicielle requise pour le serveur est la même que celle des serveurs frontaux. Pour plus d’informations sur la configuration logicielle requise, voir [prise en charge du système d’exploitation serveur et outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation relative à la prise en charge.

Pour les conférences Web, Lync Server 2013 nécessite également Office Web Apps et Office Web Apps Server (auparavant appelé Companion Server) pour gérer les présentations PowerPoint. Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Pour les conférences rendez-vous, le service d’application, les applications de surveillance des conférences et les annonces de conférences présentent les mêmes exigences relatives au système d’exploitation que les serveurs frontaux. Pour plus d’informations sur la configuration logicielle requise, voir [prise en charge du système d’exploitation serveur et outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation relative à la prise en charge.

L’application assistance de conférence et d’annonce de conférences nécessite que le runtime du format Windows Media soit installé sur les serveurs frontaux. Windows Media Format Runtime est requis pour lire des fichiers Windows Media audio (WMA) qui sont utilisés pour la musique en attente, des noms enregistrés et des invites. À l’exception de Windows Server 2012 et de Windows Server 2012 R2, le runtime du format Windows Media Runtime est automatiquement installé dans le cadre de l’expérience de bureau Windows lorsque vous exécutez le programme d’installation, mais vous devrez peut-être redémarrer l’ordinateur. Par conséquent, nous vous conseillons de procéder à l’installation dans le cadre de l’expérience de bureau Windows, qui inclut le runtime du format Windows Media, avant d’exécuter le programme d’installation. Windows Server 2012 et Windows Server 2012 R2 nécessitent Microsoft Media Foundation.

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>Exigences relatives aux ports pour les conférences rendez-vous

Le tableau suivant décrit les ports utilisés par les conférences rendez-vous. Si vous utilisez un équilibreur de charge, assurez-vous que l’équilibrage de charge est configuré pour les ports utilisés par toutes les applications qui s’exécutent dans le pool.

Ces ports sont les paramètres par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer**. Pour plus d’informations sur cette applet de connexion, consultez la documentation Lync Server Management Shell.

<div>


> [!NOTE]  
> Toutes les instances de la même application dans un pool utilisent le même port d’écoute SIP.



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>Ports utilisés par les conférences rendez-vous

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numéro de port</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5072</p></td>
<td><p>Utilisé par l’application de surveillance des conférences pour les demandes d’écoute SIP</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>Utilisé par l’application d’annonce de conférence pour les demandes d’écoute SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>Clients pris en charge pour les conférences rendez-vous

Vous pouvez utiliser le client suivant pour planifier des conférences locales prenant en charge l’accès rendez-vous :

  - Complément réunion en ligne pour Lync 2013 (installé automatiquement lors de l’installation de Lync 2013 ou participant)

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>Configuration requise pour la page des paramètres de conférence rendez-vous

La page des paramètres de conférence rendez-vous prend en charge les combinaisons de systèmes d’exploitation et de navigateurs Web décrits dans le tableau suivant.

<div>


> [!NOTE]  
> les versions 32 bits et 64 bits des systèmes d’exploitation sont prises en charge.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Systèmes d’exploitation et navigateurs web pris en charge

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Système d’exploitation</th>
<th>Navigateur web</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows 7</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Firefox</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Internet Explorer 7</p></td>
</tr>
<tr class="odd">
<td><p>Mac OS</p></td>
<td><p>Firefox</p>
<p>Safari</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>Exigences relatives aux fichiers audio pour les conférences rendez-vous

Lync Server 2013 ne prend pas en charge la personnalisation des invites vocales et de la musique pour les conférences rendez-vous. Toutefois, si vous avez un besoin professionnel qui nécessite que vous deviez modifier les fichiers audio par défaut, voir l’article 961177 de la base de connaissances Microsoft, [Comment personnaliser les invites vocales ou les fichiers audio pour les conférences rendez-vous dans Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

Vous pouvez également utiliser l’utilitaire de gestion des [invites de voix personnalisées du surveillant des conférences Microsoft Lync Server](http://go.microsoft.com/fwlink/p/?linkid=396880) , qui permet aux administrateurs de remplacer les invites vocales par défaut utilisées lorsqu’un appelant de téléphone rejoint une réunion Lync à l’aide d’invites personnalisées afin de fournir une autre utilisation de la réunion. Les invites vocales personnalisées peuvent être installées sur un serveur exécutant Lync Server 2010 ou Lync Server 2013, Enterprise ou Standard Edition.

L’application du service de conférence et l’application d’annonce présentent les exigences suivantes concernant la musique en attente, le nom enregistré et les fichiers d’invite audio :

  - Format de fichier audio Windows Media (.wma)

  - Mono 16 bits

  - Vitesse de transmission constante (CBR) 2 passes 48 Kbits/s

  - Niveau de voix à -24 Db

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>Exigences utilisateur pour la Conférence rendez-vous

Les utilisateurs de la conférence rendez-vous doivent avoir un numéro de téléphone ou de poste unique rattaché à leur compte. Cette exigence n’empêche pas l’authentification dans le cadre de la conférence rendez-vous. Utilisateurs d’entreprise (c’est-à-dire, les utilisateurs disposant d’informations d’identification de services de domaine Active Directory et de compte Lync au sein de votre organisation) entrent leur numéro de téléphone (ou leur extension) et un code confidentiel (PIN) pour se connecter aux conférences en tant que utilisateur authentifié.

</div>

</div>

<span> </span>

</div>

</div>

</div>

