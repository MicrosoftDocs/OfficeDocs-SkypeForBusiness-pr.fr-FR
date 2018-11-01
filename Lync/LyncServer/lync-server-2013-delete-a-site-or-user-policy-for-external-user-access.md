---
title: "Lync Server 2013 : Supp. d’une strat. ut. ou de site pour l’accès des ut. ext."
TOCTitle: Suppression d’une stratégie utilisateur ou de site pour l’accès des utilisateurs externes
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg521013(v=OCS.15)
ms:contentKeyID: 49297553
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une stratégie utilisateur ou de site pour l’accès des utilisateurs externes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-22_

Vous pouvez supprimer n’importe quelle stratégie de site ou stratégie utilisateur listée dans la page **Stratégie d’accès externe** du Panneau de configuration Lync Server. La suppression de la stratégie globale n’entraîne pas la suppression effective de cette dernière ; celle-ci est uniquement réinitialisée en fonction de ses paramètres par défaut, lesquels n’incluent pas la prise en charge des options relatives à l’accès des utilisateurs externes. Pour plus d’informations sur la réinitialisation de la stratégie globale, reporrtez-vous à [Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).

## Pour supprimer une stratégie de site ou d’utilisateur pour l’accès des utilisateurs externes

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Cliquez sur **Accès des utilisateurs externes** , puis sur **Stratégie d’accès externe** .

4.  Sous l’onglet **Stratégie d’accès externe** , cliquez sur la stratégie de site ou d’utilisateur à supprimer, cliquez sur **Modifier** , puis cliquez sur **Supprimer** .

5.  Dans l’invite de confirmation de la suppression, cliquez sur **OK** .

## Suppimer des stratégjes de code confidentiel via les applets de commande Windows PowerShell

ll est possible de supprimer des stratégies d’accès externe à l’aide de Windows PowerShell et de l’applet de commande Remove-CsExternalAccessPolicy (exécutable depuis le Lync Server 2013 Management Shell ou une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).).

## Supprimer une stratégie d’accès externe donnée

  - Cette commande permet de supprimer la stratégie d’accès externe appliquée au site Redmond :
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

## Supprimer toutes les stratégies d’accès externes appliquées au niveau de l’étendue Utilisateur

  - Cette commande permet de supprimer toutes les stratégies d’accès externe configurées au niveau de l’étendue Utilisateur :
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

## Supprimer toutes les stratégies d’accès externe losque l’accès des utilisateurs externes est désactivé

  - Cette commande permet de supprimer toutes les stratégies d’accès externe dans lesquelles l’accès des utilisateurs extérieurs a été désactivé :
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

Pour plus d’informations, reportez-vous à la rubrique d’aide sur l’applet de commande [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy).

