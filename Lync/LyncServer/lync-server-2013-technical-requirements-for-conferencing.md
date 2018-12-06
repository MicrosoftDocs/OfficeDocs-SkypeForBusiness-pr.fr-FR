---
title: Configuration technique requise pour les conférences dans Lync Server 2013
TOCTitle: Configuration technique requise pour les conférences
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425889(v=OCS.15)
ms:contentKeyID: 49296948
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration technique requise pour les conférences dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Dans le cas de Lync Server 2013, les fonctionnalités de conférence rendez-vous, de conférence A/V, de conférence par messagerie instantanée et de conférence web s’exécutent toujours sur les serveurs frontaux.

Cette section présente la configuration matérielle et logicielle requise pour ces serveurs ainsi que les types de colocalisation pris en charge.

La conférence rendez-vous est une fonctionnalité qui intègre divers composants. Certains de ces composants sont spécifiques à la conférence rendez-vous et d’autres sont des composants Voix Entreprise. Cette section décrit la configuration requise pour les composants spécifiques à la conférence rendez-vous. Pour plus d’informations sur la configuration requise pour le serveur de médiation et la passerelle de réseau téléphonique commuté (RTC), reportez-vous à [Composant Serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md) et [Composants et topologies utilisés pour le serveur de médiation dans Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) dans la documentation de planification.

## Configuration matérielle requise

La conférence web et la conférence A/V étant colocalisées avec le serveur frontal, la configuration matérielle requise du serveur est identique à celle des serveurs frontaux. Pour plus d’informations sur la configuration matérielle requise, reportez-vous à [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge. Les composants ci-dessous, qui sont nécessaires à la conférence rendez-vous, ont également besoin d’une configuration matérielle analogue à celle des serveurs frontaux:

  - service d’application

  - application Intendant Conférence

  - application d’annonce de conférence

La configuration matérielle requise pour le serveur frontal est la même que pour de nombreux autres rôles serveur dans Lync Server 2013. Elle est décrite dans le tableau ci-dessous.

## Configuration logicielle requise

La conférence web et la conférence A/V étant colocalisées avec le serveur frontal, la configuration logicielle requise du serveur est identique à celle des serveurs frontaux. Pour plus d’informations sur la configuration logicielle requise, reportez-vous à [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

Pour la conférence web, Lync Server 2013 a également besoin d’Office Web Apps et d’Office Web Apps Server (anciennement appelé Serveur WAC) pour gérer les présentations PowerPoint. Pour plus d’informations, reportez-vous à [Configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Pour la conférence rendez-vous, le service d’application, l’application Intendant Conférence et l’application d’annonce de conférence nécessitent la même configuration concernant le système d’exploitation que les serveurs frontaux. Pour plus d’informations sur la configuration logicielle requise, reportez-vous à [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

Pour l’application Intendant Conférence et l’application d’annonce de conférence, le module d’exécution du format Windows Media doit être installé sur les serveurs frontaux. Ce module est nécessaire pour lire les fichiers audio Windows Media (WMA) d’attente musicale, les noms enregistrés et les invites. À l’exception de Windows Server 2012 et Windows Server 2012 R2, le module d’exécution du format Windows Media est installé automatiquement en même temps que l’expérience Bureau Windows lors de l’exécution du programme d’exécution, mais vous pouvez être amené à redémarrer l’ordinateur. Par conséquent, avant d’exécuter le programme d’installation, nous vous recommandons d’installer le module d’exécution du format Windows Media en même temps que l’expérience Bureau Windows, à laquelle il est intégré. Windows Server 2012 et Windows Server 2012 R2 nécessitent Microsoft Media Foundation.

## Configuration requise pour les ports dans le cadre de la conférence rendez-vous

Le tableau ci-dessous décrit les ports utilisés par la fonctionnalité de conférence rendez-vous. Si vous utilisez un dispositif d’équilibrage de charge, vérifiez qu’il est configuré pour les ports utilisés par les applications appelées à s’exécuter dans le pool.

Ces ports sont les paramètres par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer**. Pour plus d’informations sur cette applet de commande, reportez-vous à la documentation de Lync Server Management Shell.

> [!NOTE]  
> Toutes les instances d’une même application présentes dans un pool utilisent le même port d’écoute SIP.

### Ports utilisés par la fonctionnalité de conférence rendez-vous

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
<td><p>Utilisé par l’application Intendant Conférence pour les demandes d’écoute SIP</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>Utilisé par l’application d’annonce de conférence pour les demandes d’écoute SIP</p></td>
</tr>
</tbody>
</table>


## Clients pris en charge pour la conférence rendez-vous

Vous pouvez utiliser le client suivant pour planifier des conférences locales prenant en charge un accès entrant :

  - complément de réunion en ligne pour Lync 2013 (installé automatiquement en même temps que Lync 2013 ou Participant)

## Configuration requise pour la page Paramètres de conférence rendez-vous

L’page Paramètres de conférence rendez-vous prend en charge les combinaisons de systèmes d’exploitation et de navigateurs indiquées dans le tableau suivant.

> [!NOTE]  
> Les versions 32 bits et 64 bits des systèmes d’exploitation sont prises en charge.

### Systèmes d’exploitation et navigateurs web pris en charge

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


## Exigences concernant les fichiers audio pour la conférence rendez-vous

Lync Server 2013 ne prend pas en charge la personnalisation de la musique et des invites vocales pour les conférences rendez-vous. Cependant, si vos besoins professionnels sont tels que vous devez modifier les fichiers audio par défaut, reportez-vous à l’article 961177 de la base de connaissances Microsoft, [Procédure de personnalisation des invites vocales ou des fichiers de musique pour une conférence rendez-vous dans Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

Vous pouvez également vous servir de l’utilitaire de gestion [Invites vocales personnalisées destinées aux participants d’une conférence iMicrosoft Lync Server](http://go.microsoft.com/fwlink/p/?linkid=396880), qui permet aux administrateurs de remplacer les invites vocales par défaut utilisées lorsqu’un appelant rejoint une réunion Lync par des invites personnalisées pour fournir une autre expérience d’accès aux conférences. Les invites vocales personnalisées peuvent être installées sur un serveur exécutant Lync Server 2010 ou 2013 (Enterprise ou Standard Edition).

L’application Intendant Conférence et l’application d’annonce de conférence imposent les conditions suivantes en ce qui concerne l’attente musicale, le nom enregistré et les fichiers d’invite audio :

  - Format de fichier audio Windows Media (.wma)

  - Mono 16 bits

  - CBR (vitesse de transmission constante) 2 passes 48 Kbits/s

  - Niveau de voix à -24 Db

## Exigences imposées aux utilisateurs de la conférence rendez-vous

Les utilisateurs de la conférence rendez-vous doivent avoir un numéro de téléphone ou de poste unique rattaché à leur compte. Cette exigence n’empêche pas l’authentification dans le cadre de la conférence rendez-vous. Les utilisateurs de l’entreprise (autrement dit, les utilisateurs qui disposent d’informations d’identification pour les services de domaine Active Directory et de comptes Lync Server au sein de votre organisation) entrent leur numéro de téléphone (ou de poste) ainsi qu’un code confidentiel pour accéder aux conférences en tant qu’utilisateurs authentifiés.

