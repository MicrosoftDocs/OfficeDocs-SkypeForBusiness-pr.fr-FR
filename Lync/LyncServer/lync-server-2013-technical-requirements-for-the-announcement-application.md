---
title: 'Lync Server 2013 : Configuration technique requise pour l’application Annonces'
TOCTitle: Configuration technique requise pour l’application Annonces
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205413(v=OCS.15)
ms:contentKeyID: 49299428
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration technique requise pour l’application Annonces dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-07_

Cette section décrit les conditions techniques requises suivantes pour l’application d’annonce:

  - Configuration matérielle requise

  - Configuration logicielle requise

  - Conditions requises en matière de ports

  - Conditions requises pour les fichiers audio

## Configuration matérielle requise

L’application d’annonce suit la même configuration matérielle requise que les serveurs frontaux. Pour plus d’informations sur la configuration matérielle requise, reportez-vous à [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.

## Configuration logicielle requise

L’application d’annonce suit les mêmes exigences en matière de système d’exploitation et de logiciels que les serveurs frontaux. Pour plus d’informations sur la configuration logicielle requise, reportez-vous à [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

Le module d’exécution du format Windows Media doit être installé sur tous les serveurs frontaux ou les serveurs Standard Edition exécutant l’application d’annonce pour les serveurs exécutant Windows Server 2008 R2, ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2. Pour Windows Server 2008 R2, le module d’exécution du format Windows Media est installé dans le cadre de l’expérience Bureau Windows. Le module d’exécution du format Windows Media ou Microsoft Media Foundation est requis pour les fichiers Windows Media Audio (.wma) lus par l’application d’annonce pour les annonces et la musique.

## Configuration requise pour les ports

L’application d’annonce utilise les ports suivants :

  - **Port 5071**   Utilisé pour les requêtes d’écoute SIP

> [!NOTE]  
> Ce port est le paramètre par défaut, que vous pouvez modifier en utilisant l’applet de commande <strong>Set-CsApplicationServer</strong>. Pour plus d’informations sur cette applet de commande, reportez-vous à la documentation Lync Server Management Shell.

## Conditions requises pour les fichiers audio

L’application d’annonce prend en charge les formats de fichiers Wave (.wav) et Windows Media audio (.wma) pour la musique et les annonces. Les conditions requises pour les fichiers audio pour l’application d’annonce sont identiques à celles de l’application Response Group. Pour plus d’informations, reportez-vous à [Configuration technique requise pour Response Group dans Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

