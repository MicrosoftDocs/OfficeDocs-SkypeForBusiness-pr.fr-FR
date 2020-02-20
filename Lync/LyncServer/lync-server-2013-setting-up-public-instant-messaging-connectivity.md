---
title: 'Lync Server 2013 : configuration de la connectivité PIC (public Instant Messaging Connectivity)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4887e419e45f6b6fb165dc7efff407332f3e150a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Configuration de la connectivité de messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Si votre organisation souhaite prendre en charge la connectivité PIC avec AOL, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour demander le certificat. À la place, effectuez les étapes de la procédure suivante.

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>Configuration de la connectivité PIC

1.  Sur le serveur frontal, ouvrez le Générateur de topologie. Développez les pools Edge, puis cliquez avec le bouton droit sur votre serveur Edge ou votre pool de serveurs Edge. Sélectionnez Modifier les propriétés.

2.  Dans Modifier les propriétés sous Général, sélectionnez Activer la fédération pour ce pool Edge (port 5061). Cliquez sur OK.

3.  Cliquez sur Action, sélectionnez Topologie, puis Publier. Dans la page Publier la topologie, cliquez sur Suivant. Quand la publication est terminée, cliquez sur Terminer.

4.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur Installer ou mettre à jour le système Lync Server, puis sur Installer ou supprimer des composants Lync Server. Cliquez sur Réexécuter.

5.  Dans Installer les composants Lync Server, cliquez sur Suivant. L’écran de résumé affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Pour créer une demande de certificat pour l’interface externe du serveur Edge, afin de prendre en charge la connectivité PIC avec AOL

1.  Lorsque le modèle requis est à la disposition de l’autorité de certification, utilisez l’applet de commande Windows PowerShell suivante depuis le serveur Edge pour demander le certificat :
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Le nom de certificat par défaut du modèle utilisé pour Lync Server est le serveur Web. Ne spécifiez \<le nom\> du modèle que si vous devez utiliser un modèle différent du modèle par défaut.
    
    <div>
    

    > [!IMPORTANT]  
    > Si votre organisation souhaite prendre en charge la connectivité PIC avec AOL, vous devez utiliser Windows PowerShell au lieu de l’Assistant Certificat pour demander que le certificat soit attribué au serveur Edge externe pour le service Edge d’accès. Ceci est dû au fait que le modèle Serveur web de l’autorité de certification utilisé par l’Assistant Certificat pour demander un certificat ne prend pas en charge la configuration EKU (utilisation avancée de la clé) sur le client. Avant d’utiliser Windows PowerShell pour créer le certificat, l’administrateur de l’autorité de certification doit créer et déployer un nouveau modèle qui prend en charge l’utilisation améliorée de la variable client.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

