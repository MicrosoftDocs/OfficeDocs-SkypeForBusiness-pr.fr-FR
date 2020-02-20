---
title: 'Lync Server 2013 : création d’un filtre de transfert de fichiers pour un site spécifique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a374cb234567c5aeb44ce6071f6e67559c5159ec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Créer un nouveau filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

En plus de modifier le filtre de transfert de fichiers global, vous pouvez configurer des filtres de transfert de fichiers personnalisés pour des sites spécifiques au sein de votre déploiement Lync Server 2013. Pour plus d’informations sur le filtrage du transfert de fichiers, voir [Configuring File Transfer and URL Filtering for Instant Messaging (im) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>Pour créer un filtre de transfert de fichiers adapté à un site spécifique

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

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

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modifier le filtre d’URL par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

