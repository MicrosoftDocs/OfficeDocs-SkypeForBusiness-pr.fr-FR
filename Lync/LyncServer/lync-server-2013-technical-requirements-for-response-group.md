---
title: 'Lync Server 2013 : Configuration technique requise pour Response Group'
TOCTitle: Configuration technique requise pour Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204863(v=OCS.15)
ms:contentKeyID: 49297081
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration technique requise pour Response Group dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette section décrit les conditions techniques requises suivantes pour l’application Response Group:

  - Configuration matérielle requise

  - Configuration logicielle requise

  - Conditions requises en matière de ports

  - Conditions requises pour les fichiers audio

  - Conditions requises pour l’outil de configuration Response Group

## Configuration matérielle requise

L’application Response Group suit la même configuration matérielle requise que les serveurs frontaux. Pour plus d’informations sur la configuration matérielle requise, reportez-vous à [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.

## Configuration logicielle requise

L’application Response Group suit les mêmes exigences en matière de système d’exploitation et de logiciels que les serveurs frontaux. Pour plus d’informations sur la configuration logicielle requise, reportez-vous à [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

Si vous utilisez des fichiers audio Windows Media (.wma) pour la musique et les annonces Response Group, tous les serveurs frontaux ou serveurs Standard Edition qui exécutent l’application Response Group doivent disposer du module d’exécution du format Windows Media installé pour les serveurs exécutant Windows Server 2008 R2 ou de Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2. Pour Windows Server 2008 R2, le module d’exécution du format Windows Media est installé dans le cadre de l’expérience Bureau Windows.

Pour plus d’informations sur les conditions requises pour l’audio, reportez-vous à « Conditions requises pour les fichiers audio » dans la suite de cette section.

## Configuration requise pour les ports

L’application Response Group utilise les ports suivants :

  - **Port 5071**   Utilisé pour les requêtes d’écoute SIP

  - **Port 8404**   Utilisé pour les communications entre les serveurs
    
    > [!NOTE]  
    > Ce port est utilisé pour le service d’établissement des correspondances et est nécessaire quand l’application Response Group est déployée dans un pool qui comporte plusieurs serveur frontal.

> [!NOTE]  
> Ces ports sont les paramètres par défaut que vous pouvez modifier à l’aide de l’applet de commande <strong>Set-CsApplicationServer</strong>. Pour plus d’informations sur cette applet de commande, reportez-vous à la documentation de Lync Server Management Shell.

## Conditions requises pour les fichiers audio

L’application Response Group prend en charge le format de fichier Wave (.wav) et le format de fichier audio Windows Media (.wma) pour les messages, la musique d’attente ou les questions à réponse vocale interactive Response Group.

Le format de fichier audio Windows Media nécessite que le runtime du format Windows Media soit installé sur les serveurs frontaux exécutant Windows Server 2008 R2 et Windows Server 2008. Pour plus d’informations, reportez-vous à « Configuration logicielle requise » plus haut dans cette section.

## Formats de fichiers Wave pris en charge

Tous les fichiers Wave doivent répondre aux conditions suivantes :

  - fichier 8 bits ou 16 bits ;

  - format LPCM (Linear Pulse Code Modulation), A-Law ou mu-Law ;

  - mono ou stéréo ;

  - 4 Mo ou moins.

Pour des performances de fichiers Wave optimales, nous vous recommandons d’utiliser un fichier Wave correspondant au profil suivant : 16 kHz, Mono, 16 bits.

## Formats de fichiers audio Windows Media pris en charge

Si vous utilisez un fichier audio Windows Media, prévoyez d’utiliser de faibles vitesses de transmission et vérifiez les performances de votre système quand il est surchargé.

Vous pouvez utiliser Microsoft Expression Encoder 4 pour convertir un fichier au format audio Windows Media. Pour télécharger Expression Encoder 4, reportez-vous à [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).

## Conditions requises pour l’outil de configuration Response Group

L’outil de configuration Response Group prend en charge les combinaisons de systèmes d’exploitation et de navigateurs indiquées dans le tableau suivant.

> [!NOTE]  
> Les versions 32 bits ou 64 bits des systèmes d’exploitation sont prises en charge. Seules les versions 32 bits d’Internet Explorer sont prises en charge.

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
<td><p>Windows Vista avec Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 avec Service Pack 1</p></td>
<td><p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 avec Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p></td>
</tr>
<tr class="even">
<td><p></p>
<p></p>
<p></p>
<p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 avec Service Pack 1</p></td>
<td><p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p></td>
</tr>
</tbody>
</table>


## Console des agents Response Group

La console des agents prend en charge les combinaisons de systèmes d’exploitation et de navigateurs indiquées dans le tableau suivant.

> [!NOTE]  
> Les versions 32 bits ou 64 bits des systèmes d’exploitation sont prises en charge. Seules les versions 32 bits d’Internet Explorer sont prises en charge.

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
<td><p>Windows Vista avec Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 avec Service Pack 1</p></td>
<td><p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 avec Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 avec Service Pack 1</p></td>
<td><p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td></td>
</tr>
</tbody>
</table>

