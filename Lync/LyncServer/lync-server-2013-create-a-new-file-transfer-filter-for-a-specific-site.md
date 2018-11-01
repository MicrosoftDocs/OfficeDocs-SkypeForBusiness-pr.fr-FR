---
title: Créer un filtre de transfert de fichiers pour un site spécifique
TOCTitle: Créer un filtre de transfert de fichiers pour un site spécifique
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182589(v=OCS.15)
ms:contentKeyID: 49298892
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer un filtre de transfert de fichiers pour un site spécifique

 

_**Dernière rubrique modifiée :** 2012-10-18_

Vous pouvez non seulement modifier les filtres de transfert de fichiers globaux, mais également les configurer pour des sites spécifiques dans votre déploiement Lync Server 2013. Pour plus d’informations sur le filtrage du transfert de fichiers, voir [Configuration du transfert de fichiers et du filtrage des URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

## Pour créer un filtre de transfert de fichiers adapté à un site spécifique

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Messagerie instantanée et présence**, puis cliquez sur **Filtre de fichier**.

4.  Dans la page **Filtre de fichier**, cliquez sur **Nouveau**.

5.  Dans la boîte de dialogue **Sélectionner un site**, cliquez sur le site pour lequel vous souhaitez créer le filtre de transfert de fichiers, puis cliquez sur **OK**.

6.  Dans **Nouveau filtre de fichier**, activez la case à cocher **Activer le filtre de fichier**.

7.  Dans la zone de liste déroulante **Transfert de fichiers**, cliquez sur **Bloquer tout** ou **Bloquer des types de fichiers spécifiques**.

8.  Si vous avez cliqué sur **Bloquer tout**, passez à l’étape 10.

9.  Si vous avez cliqué sur **Bloquer des types de fichiers spécifiques**, procédez comme suit :
    
    1.  Cliquez sur **Sélectionner** pour modifier la liste par défaut des extensions de type de fichier à bloquer.
    
    2.  Dans la boîte de dialogue **Sélectionner un type de fichier**, sélectionnez les types de fichiers que vous voulez bloquer ou autoriser en ajoutant ou en supprimant leur extension dans les catégories sous **Sélectionner des extensions de type de fichier**.
    
    3.  Si l’extension du type de fichier que vous souhaitez bloquer n’apparaît pas, tapez-la dans la zone de texte sous **Ajoutez des extensions de type de fichier à la liste**, puis cliquez sur **Ajouter**.
    
    4.  Cliquez sur **OK**.

10. Cliquez sur **Valider**.

## Voir aussi

#### Tâches

[Configuration du transfert de fichiers et du filtrage des URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Créer un filtre d’URL pour gérer les liens hypertexte dans des conversations de messagerie instantanée](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Modifier le filtre de transfert de fichiers par défaut](lync-server-2013-modify-the-default-file-transfer-filter.md)  

#### Concepts

[Modifier le filtre d’URL par défaut](lync-server-2013-modify-the-default-url-filter.md)

