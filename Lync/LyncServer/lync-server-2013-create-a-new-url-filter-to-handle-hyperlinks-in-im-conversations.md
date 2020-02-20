---
title: Créer un nouveau filtre d’URL pour gérer les liens hypertexte dans les conversations de messagerie instantanée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 250533f8de89eb1cd5aaa72d8f66cfd0800a1bc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-26_

En plus de modifier le filtre d’URL globales, vous pouvez configurer des filtres d’URL personnalisés pour des sites individuels au sein de votre déploiement Lync Server 2013. Pour plus d’informations sur le filtrage des URL, voir [Configuring File Transfer and URL Filtering for Instant Messaging (im) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-new-url-filter"></a>Pour créer un filtre d’URL

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Messagerie instantanée et présence**, puis cliquez sur **Filtre d’URL**.

4.  Dans la page **Filtre d’URL**, cliquez sur **Nouveau**.

5.  Dans la boîte de dialogue **Sélectionner un site**, cliquez sur le site pour lequel vous souhaitez créer le filtre d’URL, puis cliquez sur **OK**.

6.  Dans la boîte de dialogue **Nouveau filtre d’URL**, activez la case à cocher **Activer le filtre d’URL** pour activer le filtrage d’URL sur le site.

7.  Pour bloquer une URL active qui contient un fichier dont l’extension figure sous **Extensions de types de fichiers à bloquer** dans **Modifier le filtre de fichiers**, activez la case à cocher **Bloquer les URL avec extension de fichier**.

8.  Dans la zone de liste déroulante **Préfixe de lient hypertexte**, cliquez sur l’option correspondant à la manière dont vous voulez gérer les URL dans les conversations de messages instantanés.
    
    Lorsque la case à cocher **Autoriser le message** est activée, un message d’avertissement peut être envoyé à l’utilisateur lors de l’envoi des liens hypertexte autorisés à être envoyés.

9.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Créer un nouveau filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modifier le filtre d’URL par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

