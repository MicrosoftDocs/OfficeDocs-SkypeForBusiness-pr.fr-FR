---
title: 'Lync Server 2013 : Configuration technique requise pour le parcage d’appel'
TOCTitle: Configuration technique requise pour le parcage d’appel
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204818(v=OCS.15)
ms:contentKeyID: 49296910
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration technique requise pour le parcage d’appel dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette section décrit les exigences techniques du parcage d’appel, à savoir :

  - Configuration matérielle requise

  - Configuration logicielle requise

  - Conditions requises en matière de ports

  - Conditions requises pour les fichiers audio

## Configuration matérielle requise

L’application de parcage d’appel suit la même configuration matérielle requise que les serveurs frontaux. Pour plus d’informations sur la configuration matérielle requise, reportez-vous à [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.

## Configuration logicielle requise

L’application de parcage d’appel suit les mêmes exigences en matière de système d’exploitation et de logiciels que les serveurs frontaux. Pour plus d’informations sur la configuration logicielle requise, reportez-vous à [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

Tous les serveurs frontaux et les serveurs Standard Edition sur lesquels l’application de parcage d’appel est déployée doivent disposer du module d’exécution du format Windows Media, si ces serveurs exécutent Windows Server 2008 R2, ou de Microsoft Media Foundation pour les serveurs qui exécutent Windows Server 2012 ou Windows Server 2012 R2. En ce qui concerne Windows Server 2008 R2, le module d’exécution du format Windows Media est installé en même temps que l’expérience Bureau Windows. Le module d’exécution du format Windows Media ou Microsoft Media Foundation sont nécessaires pour permettre à l’parcage d’appel de lire les fichiers d’attente musicale au format Windows Media Audio (.wma).

## Configuration requise pour les ports

L’application de parcage d’appel utilise les ports suivants :

  - **Port 5075** : utilisé pour les demandes d’écoute SIP.

> [!NOTE]  
> Ce port est un paramètre par défaut que vous pouvez modifier à l’aide de l’applet de commande <strong>Set-CsApplicationServer</strong>. Pour plus d’informations sur cette applet de commande, reportez-vous à la documentation de Lync Server Management Shell.

## Conditions requises pour les fichiers audio

L’application de parcage d’appel prend uniquement en charge les fichiers d’attente musicale au format Windows Media Audio (.wma). Pour personnaliser les fichiers d’attente musicale, vous pouvez utiliser Microsoft Expression Encoder 4. Pour télécharger Expression Encoder 4, reportez-vous à « Expression Encoder 4 » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843). Utilisez l’outil pour convertir le fichier au format .wma. Le format recommandé pour les fichiers d’attente musicale du parcage d’appel est Windows Media Audio 9,44 kHz, 16 bits, Mono, CBR, 32 Kbits/s.

> [!NOTE]  
> Le fichier converti est lu sur le téléphone à seulement 16 kHz, même s’il a été enregistré à 44 kHz.
