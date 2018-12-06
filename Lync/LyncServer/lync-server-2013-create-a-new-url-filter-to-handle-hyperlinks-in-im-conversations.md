---
title: "Créer un filtre URL pour gérer les liens hypert. dans des conv. de mess. Inst."
TOCtitle: "Créer un filtre URL pour gérer les liens hypert. dans des conv. de mess. Inst."
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182590(v=OCS.15)
ms:contentKeyID: 49298907
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer un filtre d’URL pour gérer les liens hypertexte dans des conversations de messagerie instantanée

 

_**Dernière rubrique modifiée :** 2012-09-26_

En plus de modifier le filtre d’URL global, vous pouvez configurer des filtres d’URL personnalisés pour des sites individuels dans votre déploiement Lync Server 2013. Pour plus d’informations sur le filtrage d’URL, voir [Configuration du transfert de fichiers et du filtrage des URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

## Pour créer un filtre d’URL

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Messagerie instantanée et présence**, puis cliquez sur **Filtre d’URL**.

4.  Dans la page **Filtre d’URL**, cliquez sur **Nouveau**.

5.  Dans la boîte de dialogue **Sélectionner un site**, cliquez sur le site pour lequel vous souhaitez créer le filtre d’URL, puis cliquez sur **OK**.

6.  Dans la boîte de dialogue **Nouveau filtre d’URL**, activez la case à cocher **Activer le filtre d’URL** pour activer le filtrage d’URL sur le site.

7.  Pour bloquer une URL active qui contient un fichier dont l’extension figure sous **Extensions de types de fichiers à bloquer** dans **Modifier le filtre de fichiers**, activez la case à cocher **Bloquer les URL avec extension de fichier**.

8.  Dans la zone de liste déroulante **Préfixe de lient hypertexte**, cliquez sur l’option correspondant à la manière dont vous voulez gérer les URL dans les conversations de messages instantanés.
    
    Lorsque la case à cocher **Autoriser le message** est activée, un message d’avertissement peut être envoyé à l’utilisateur lors de l’envoi des liens hypertexte autorisés à être envoyés.

9.  Cliquez sur **Valider**.

## Voir aussi

#### Tâches

[Configuration du transfert de fichiers et du filtrage des URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Créer un filtre de transfert de fichiers pour un site spécifique](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Modifier le filtre de transfert de fichiers par défaut](lync-server-2013-modify-the-default-file-transfer-filter.md)  

#### Concepts

[Modifier le filtre d’URL par défaut](lync-server-2013-modify-the-default-url-filter.md)

