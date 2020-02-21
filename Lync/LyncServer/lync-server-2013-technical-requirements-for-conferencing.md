---
title: Configuration technique requise pour Lync Server 2013 pour les conférences
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
ms.openlocfilehash: b6f28effa3ac80f4a2bca1fa062fcc3dfafb5d7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Configuration technique requise pour les conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-25_

Pour Lync Server 2013, les fonctionnalités de conférence rendez-vous, de conférence A/V, de conférence par messagerie instantanée et de conférence Web s’exécutent toujours sur des serveurs frontaux.

Cette section présente la configuration matérielle et logicielle requise pour ces serveurs ainsi que les types de colocalisation pris en charge.

La conférence rendez-vous est une fonctionnalité qui intègre divers composants. Certains des composants sont spécifiques à la Conférence rendez-vous et d’autres sont des composants voix entreprise. Cette section décrit la configuration requise pour les composants spécifiques à la conférence rendez-vous. Pour plus d’informations sur la configuration requise pour le serveur de médiation et la passerelle RTC (réseau téléphonique commuté), voir [composant serveur de médiation dans Lync server 2013](lync-server-2013-mediation-server-component.md) et [composants et topologies pour le serveur de médiation dans Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) dans la documentation de planification.

<div>

## <a name="hardware-requirements"></a>Configuration matérielle requise

Étant donné que les conférences Web et les conférences A/V sont colocalisées avec le serveur frontal, la configuration matérielle requise du serveur est la même que pour les serveurs frontaux. Pour plus d’informations sur la configuration matérielle requise, voir [Server Hardware Platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge. Les composants suivants requis pour la Conférence rendez-vous ont également la configuration matérielle requise pour les serveurs frontaux :

  - service d’application

  - application Intendant Conférence

  - application d’annonce de conférence

La configuration matérielle requise pour le serveur frontal est la même que pour de nombreux autres rôles serveur dans Lync Server 2013 sont décrits dans le tableau suivant.

</div>

<div>

## <a name="software-requirements"></a>Configuration logicielle requise

Étant donné que les conférences Web et les conférences A/V sont colocalisées avec le serveur frontal, la configuration logicielle requise du serveur est la même que pour les serveurs frontaux. Pour plus d’informations sur la configuration logicielle requise, voir [serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

Pour la conférence Web, Lync Server 2013 nécessite également Office Web Apps et Office Web Apps Server (anciennement appelé serveur WAC) pour gérer les présentations PowerPoint. Pour plus d’informations, reportez-vous à la rubrique Configuration de l' [intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Pour les applications de conférence rendez-vous, d’applications, de surveillance de conférence et d’annonce de conférence, la configuration requise du système d’exploitation est la même que pour les serveurs frontaux. Pour plus d’informations sur la configuration logicielle requise, voir [serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

Application de surveillance de conférence et application d’annonce de conférence nécessitent que le module d’exécution du format Windows Media soit installé sur les serveurs frontaux. Ce module est nécessaire pour lire les fichiers audio Windows Media (WMA) d’attente musicale, les noms enregistrés et les invites. À l’exception de Windows Server 2012 et Windows Server 2012 R2, le runtime de format Windows Media est installé automatiquement dans le cadre de l’expérience de bureau Windows lorsque vous exécutez le programme d’installation, mais vous devrez peut-être redémarrer l’ordinateur. Par conséquent, avant d’exécuter le programme d’installation, nous vous recommandons d’installer le module d’exécution du format Windows Media en même temps que l’expérience Bureau Windows, à laquelle il est intégré. Windows Server 2012 et Windows Server 2012 R2 nécessitent Microsoft Media Foundation.

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>Configuration requise pour les ports dans le cadre de la conférence rendez-vous

Le tableau suivant décrit les ports utilisés par la fonctionnalité de conférence rendez-vous. Si vous utilisez un dispositif d’équilibrage de charge, vérifiez qu’il est configuré pour les ports utilisés par les applications appelées à s’exécuter dans le pool.

Ces ports sont des paramètres par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer**. Pour plus d’informations sur cette applet de commande, voir la documentation de Lync Server Management Shell.

<div>


> [!NOTE]  
> Toutes les instances d’une même application présentes dans un pool utilisent le même port d’écoute SIP.



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>Ports utilisés par la fonctionnalité de conférence rendez-vous

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numéro du port</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5072</p></td>
<td><p>Utilisé par l’application de surveillance de conférence pour les demandes d’écoute SIP</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>Utilisé par l’application d’annonce de conférence pour les demandes d’écoute SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>Clients pris en charge pour la conférence rendez-vous

Vous pouvez utiliser le client suivant pour planifier des conférences locales prenant en charge un accès entrant :

  - Complément de réunion en ligne pour Lync 2013 (installé automatiquement lors de l’installation de Lync 2013 ou Attendee)

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>Configuration requise pour la page des paramètres de conférence rendez-vous

La page Paramètres de conférence rendez-vous prend en charge les combinaisons de systèmes d’exploitation et de navigateurs Web décrites dans le tableau suivant.

<div>


> [!NOTE]  
> Les versions 32 bits et 64 bits des systèmes d’exploitation sont prises en charge.



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
<th>Navigateur Web</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows 7</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
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
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
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

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>Exigences concernant les fichiers audio pour la conférence rendez-vous

Lync Server 2013 ne prend pas en charge la personnalisation des invites vocales et de la musique pour les conférences rendez-vous. Toutefois, si vous avez un besoin important de votre entreprise qui nécessite de modifier les fichiers audio par défaut, consultez l’article 961177 de la base de connaissances Microsoft, [Comment personnaliser les invites vocales ou les fichiers musicaux pour les conférences audio de rendez-vous dans Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

Vous pouvez également utiliser l’utilitaire de gestion des [invites vocales personnalisées du service de conférence Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkid=396880) , qui permet aux administrateurs de remplacer les invites vocales par défaut utilisées lorsqu’un appelant téléphonique rejoint une réunion Lync avec des invites personnalisées pour fournir une autre expérience d’entrée de réunion. Les invites vocales personnalisées peuvent être installées sur un serveur qui exécute Lync Server 2010 ou Lync Server 2013, Enterprise ou Standard Edition.

Application de surveillance de conférence et application d’annonce de conférence ont les exigences suivantes en matière d’attente musicale, de nom enregistré et de fichiers d’invite audio :

  - Format de fichier audio Windows Media (.wma)

  - Mono 16 bits

  - CBR (vitesse de transmission constante) 2 passes 48 Kbits/s

  - Niveau de voix à -24 Db

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>Exigences imposées aux utilisateurs de la conférence rendez-vous

Les utilisateurs de la conférence rendez-vous doivent avoir un numéro de téléphone ou de poste unique rattaché à leur compte. Cette exigence n’empêche pas l’authentification dans le cadre de la conférence rendez-vous. Les utilisateurs d’entreprise (c’est-à-dire, les utilisateurs disposant d’informations d’identification des services de domaine Active Directory et les comptes Lync Server au sein de votre organisation) entrent leur numéro de téléphone (ou poste) et un code confidentiel (PIN) pour se connecter aux conférences en tant que utilisateur authentifié.

</div>

</div>

<span> </span>

</div>

</div>

</div>

