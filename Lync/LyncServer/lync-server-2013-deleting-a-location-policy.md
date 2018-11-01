---
title: Suppression d’une stratégie d’emplacement
TOCTitle: Suppression d’une stratégie d’emplacement
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49891435
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une stratégie d’emplacement

 

_**Dernière rubrique modifiée :** 2012-10-10_

Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour appliquer des paramètres liés au système Enhanced 9-1-1 (E9-1-1) et des paramètres d’emplacement pour les utilisateurs et les contacts. La stratégie d’emplacement détermine si un utilisateur peut avoir recours au système E9-1-1 et, le cas échéant, le comportement d’un appel d’urgence. Par exemple, la stratégie d’emplacement permet de définir le numéro d’appel d’urgence (par exemple, 911 aux États-Unis, 15 en France), de déterminer si le service de sécurité de l’entreprise doit être automatiquement averti et comment l’appel doit être acheminé.

Vous pouvez configurer les stratégies d’emplacement à partir du groupe **Configuration réseau** dans le Panneau de configuration Lync Server 2013. À partir du Panneau de configuration Lync Server vous pouvez afficher, créer, modifier ou supprimer des stratégies d’emplacement. Utilisez les procédures suivantes pour supprimer une stratégie d’emplacement. Pour plus d’informations sur la création ou la modification de stratégies d’emplacement, voir [Création ou modification d’une stratégie d’emplacement](lync-server-2013-creating-or-modifying-a-location-policy.md).

## Pour supprimer une stratégie d’emplacement

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement**, sélectionnez la stratégie d’emplacement que vous souhaitez supprimer.
    
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs stratégies d’emplacement à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs stratégies. Ou, pour sélectionner toutes les stratégies, cliquez sur <strong>Sélectionner tout</strong> dans le menu <strong>Edition</strong>.

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.
    
    > [!IMPORTANT]  
    > Vous ne pouvez pas supprimer la stratégie d’emplacement globale. Si vous tentez de supprimer cette stratégie vous obtiendrez un message d’erreur et les valeurs par défaut de cette stratégie seront rétablies.

## Voir aussi

#### Tâches

[Création ou modification d’une stratégie d’emplacement](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Affichage des informations d’une stratégie d’emplacement](lync-server-2013-viewing-location-policy-information.md)

