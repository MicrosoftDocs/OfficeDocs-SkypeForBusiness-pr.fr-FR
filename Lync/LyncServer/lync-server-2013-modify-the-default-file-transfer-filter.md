---
title: 'Lync Server 2013 : modifier le filtre de transfert de fichiers par défaut'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a99847739b134c97172b26a6ebfbb2d808cdd3af
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Lync Server 2013 fournit un filtre de transfert de fichiers global qui bloque des types de fichiers spécifiques lors des activités de fichier suivantes dans votre déploiement Lync Server 2013 :

  - Demandes de transfert de fichiers pendant les conversations de messagerie instantanée

  - Chargements et téléchargements pendant l’utilisation de la fonctionnalité des documents dans le client Office Live Meeting 2007

  - Lecture multimédia pendant les conférences

En fonction des types de fichiers que vous voulez bloquer ou autoriser, vous pouvez utiliser le panneau de configuration Lync Server pour modifier le filtre global. Pour plus d’informations sur le filtrage du transfert de fichiers, voir [Configuring File Transfer and URL Filtering for Instant Messaging (im) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>Pour modifier le filtre de transfert de fichiers par défaut

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

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

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Créer un nouveau filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Modifier le filtre d’URL par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

