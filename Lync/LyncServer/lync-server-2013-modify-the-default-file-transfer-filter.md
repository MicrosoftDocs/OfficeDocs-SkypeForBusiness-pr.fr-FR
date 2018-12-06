---
title: Modifier le filtre de transfert de fichiers par défaut
TOCTitle: Modifier le filtre de transfert de fichiers par défaut
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg521017(v=OCS.15)
ms:contentKeyID: 49297794
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifier le filtre de transfert de fichiers par défaut

 

_**Dernière rubrique modifiée :** 2012-11-01_

Lync Server 2013 propose un filtre global de transfert de fichiers qui bloque les types de fichiers spécifiques au cours des activités liées aux fichiers suivantes dans votre déploiement Lync Server 2013 :

  - Demandes de transfert de fichiers pendant les conversations de messagerie instantanée

  - Chargements et téléchargements pendant l’utilisation de la fonctionnalité des documents dans le client Office Live Meeting 2007

  - Lecture multimédia pendant les conférences

Selon les types de fichiers que vous souhaitez bloquer ou autoriser, vous pouvez utiliser le Panneau de configuration Lync Server pour modifier le filtre global. Pour plus d’informations sur le filtrage du transfert de fichiers, voir [Configuration du transfert de fichiers et du filtrage des URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

## Pour modifier le filtre de transfert de fichiers par défaut

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Messagerie instantanée et présence**, puis cliquez sur **Filtre de fichier**.

4.  Dans la page **Filtre de fichier**, double-cliquez sur le filtre **Global**.

5.  Dans **Modifier le filtre de fichier**, activez la case à cocher **Activer le filtre de fichier**.

6.  Dans la zone de liste déroulante **Transfert de fichiers**, cliquez sur **Bloquer tout** ou **Bloquer des types de fichiers spécifiques**.

7.  Si vous avez cliqué sur **Bloquer tout**, passez à l’étape 9.

8.  Si vous avez cliqué sur **Bloquer des types de fichiers spécifiques**, procédez comme suit :
    
    1.  Cliquez sur **Sélectionner** pour modifier la liste par défaut des extensions de type de fichier à bloquer.
    
    2.  Dans **Sélectionner un type de fichier**, sélectionnez les types de fichiers que vous voulez bloquer ou autoriser en ajoutant ou en supprimant leur extension dans les catégories sous **Extensions de type de fichier**.
    
    3.  Si l’extension du type de fichier que vous souhaitez bloquer n’apparaît pas, tapez-la dans la zone de texte sous **Ajoutez des extensions de type de fichier à la liste**, puis cliquez sur **Ajouter**.
    
    4.  Cliquez sur **OK**.

9.  Cliquez sur **Valider**.

## Voir aussi

#### Tâches

[Configuration du transfert de fichiers et du filtrage des URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Créer un filtre de transfert de fichiers pour un site spécifique](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Créer un filtre d’URL pour gérer les liens hypertexte dans des conversations de messagerie instantanée](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  

#### Concepts

[Modifier le filtre d’URL par défaut](lync-server-2013-modify-the-default-url-filter.md)

