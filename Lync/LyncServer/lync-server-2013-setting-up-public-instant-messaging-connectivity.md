---
title: 'Lync Server 2013 : Configuration de la connectivité PIC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e77d8914a1f55ac10544591913a7347e271e9de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Configuration de la connectivité PIC dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-08_

Si votre organisation veut prendre en charge la connectivité de messagerie instantanée publique avec AOL, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour demander le certificat. À la place, suivez les étapes de la procédure suivante.

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>Configuration de la connectivité de messagerie instantanée publique

1.  Sur un serveur frontal, ouvrez le générateur de topologie. Développez pools de bords, puis cliquez avec le bouton droit sur votre serveur Edge ou sur le pool de serveurs Edge. Sélectionnez modifier les propriétés.

2.  Dans modifier les propriétés sous général, sélectionnez Activer la Fédération pour ce pool Edge (port 5061). Cliquez sur OK.

3.  Cliquez sur action, sélectionnez topologie, puis publier. Lorsque le système vous le demande, cliquez sur suivant. Lorsque la publication est terminée, cliquez sur Terminer.

4.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur installer ou mettre à jour le système serveur Lync, puis cliquez sur Configurer ou supprimer les composants Lync Server. Cliquez de nouveau sur Exécuter.

5.  Dans configurer les composants serveur Lync, cliquez sur suivant. L’écran de synthèse indique les actions à mesure qu’elles sont exécutées. Lorsque le déploiement est effectué, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Pour créer une demande de certificat pour l’interface externe du serveur de périphérie pour la prise en charge de la connectivité de messagerie instantanée publique avec AOL

1.  Lorsque le modèle requis est disponible pour l’autorité de certification, utilisez la cmdlet Windows PowerShell suivante à partir du serveur de périphérie pour demander le certificat.
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Le nom du certificat par défaut du modèle utilisé pour Lync Server est le serveur Web. Spécifiez le \<nom\> du modèle uniquement si vous devez utiliser un modèle différent du modèle par défaut.
    
    <div>
    

    > [!IMPORTANT]  
    > Si votre organisation veut prendre en charge une connectivité de messagerie instantanée publique avec AOL, vous devez utiliser Windows PowerShell au lieu de l’Assistant Certificat pour demander que le certificat soit affecté au bord externe du service Edge d’accès. En effet, le modèle de serveur Web d’autorité de certification utilisé par l’Assistant Certificat pour demander un certificat ne prend pas en charge la configuration améliorée de l’utilisation du client. Avant d’utiliser Windows PowerShell pour créer le certificat, l’administrateur de l’autorité de certification doit créer et déployer un nouveau modèle qui prend en charge l’utilisation améliorée de l’utilisation du client.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

