---
title: Affichage des informations d’une stratégie d’emplacement
TOCTitle: Affichage des informations d’une stratégie d’emplacement
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520954(v=OCS.15)
ms:contentKeyID: 49296343
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations d’une stratégie d’emplacement

 

_**Dernière rubrique modifiée :** 2012-11-01_

Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour appliquer des paramètres liés au système Enhanced 9-1-1 (E9-1-1) et des paramètres d’emplacement pour les utilisateurs et les contacts. La stratégie d’emplacement détermine si un utilisateur peut avoir recours au système E9-1-1 et, le cas échéant, le comportement d’un appel d’urgence. Par exemple, la stratégie d’emplacement permet de définir le numéro d’appel d’urgence (par exemple 911 aux États-Unis, 15 en France), de déterminer si le service de sécurité de l’entreprise doit être automatiquement averti et comment l’appel doit être acheminé.

Vous pouvez configurer des stratégies d’emplacement depuis le groupe **Configuration réseau** dans le Panneau de configuration Lync Server 2013. Le Panneau de configuration Lync Server vous permet d’afficher, de créer, de modifier ou de supprimer des stratégies d’emplacement. Utilisez les procédures suivantes pour afficher des informations sur les stratégies d’emplacement. Pour en savoir plus sur la création ou la modification des stratégies d’emplacement, voir [Création ou modification d’une stratégie d’emplacement](lync-server-2013-creating-or-modifying-a-location-policy.md).

## Pour afficher des informations sur une stratégie d’emplacement

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement**, sélectionnez la stratégie d’emplacement que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.
    
    > [!NOTE]  
    > Vous ne pouvez afficher des informations que sur une seule stratégie d’emplacement à la fois.

Une stratégie unique, appelée Globale, existe par défaut. Il n’est pas possible de supprimer ou de renommer cette stratégie. Vous pouvez cependant la modifier. Cette stratégie s’applique à tous les utilisateurs et contacts, sauf si vous créez des stratégies de site ou par utilisateur. Les stratégies par utilisateur doivent être appliquées à des utilisateurs spécifiques.

## Voir aussi

#### Tâches

[Création ou modification d’une stratégie d’emplacement](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Créer des stratégies d’emplacement dans Lync Server 2013](lync-server-2013-create-location-policies.md)  
[Création ou modification d’un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)  

#### Autres ressources

[New-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsLocationPolicy)  
[Set-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsLocationPolicy)

