---
title: 'Lync Server 2013 : Préparation de l’environnement pour VDI'
TOCTitle: Préparation de l’environnement pour VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205154(v=OCS.15)
ms:contentKeyID: 49298395
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Préparation de l’environnement Lync Server 2013 pour VDI

 

_**Dernière rubrique modifiée :** 2013-02-22_

Pour préparer l’environnement pour le plug-in VDI Lync, l’administrateur doit effectuer les étapes suivantes.

1.  Dans Lync Server 2013, assurez-vous que EnableMediaRedirection est paramétré sur TRUE pour tous les utilisateurs VDI. Pour plus d’informations, reportez-vous aux rubriques d’aide des applets de commande [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) et [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy).

2.  Sur l’ordinateur du centre de données, installer le client Lync 2013 sur tous les ordinateurs virtuels.

3.  Sur les ordinateurs locaux, installer le plug-in VDI Lync.

