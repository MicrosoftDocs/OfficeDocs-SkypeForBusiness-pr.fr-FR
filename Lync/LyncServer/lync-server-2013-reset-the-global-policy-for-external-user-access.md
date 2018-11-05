---
title: "Lync Server 2013 : Réinit. de la strat. glob. pour l’accès des ut. externes"
TOCTitle: Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182545(v=OCS.15)
ms:contentKeyID: 49297904
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-22_

Il est impossible de supprimer totalement une stratégie globale. L’utilisation de l’option **Supprimer** sur la stratégie globale la réinitialise uniquement avec les paramètres par défaut, c’est-à-dire sans prise en charge des options d’accès des utilisateurs externes.

## Pour réinitialiser la stratégie globale avec les paramètres par défaut

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe**, cliquez sur la stratégie globale, sur **Modifier**, puis sur **Supprimer**.

5.  Dans l’invite de confirmation de la suppression, cliquez sur **OK**. Un message s’affiche en haut de la page vous informant que la stratégie globale a été réinitialisée.

## Réinitialisation de la stratégie d’accès externe globale via les applets de commande Windows PowerShell

Il est possible de réinitialiser la stratégie d’accès externe globale à l’aide de Windows PowerShell et de l’applet de commande Remove-CsExternalAccessPolicy (exécutable depuis le Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).).

## Réinitialiser la stratégie d’accès externe globale

  - Cette commande redéfinit la stratégie d’accès externe globale :
    
        Remove-CsExternalAccessPolicy -Identity "global"

Pour plus d’informations, reportez-vous à la rubrique d’aide sur l’applet de commande [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy).

