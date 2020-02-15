---
title: Modifier l’action par défaut pour les clients qui ne sont pas explicitement pris en charge ou restreints
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63ff08d05c9c8c18b7f81f22b04e2168a14f1a8c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Modifier l’action par défaut pour les clients qui ne sont pas explicitement pris en charge ou restreints dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

En plus de spécifier la version des clients que vous souhaitez prendre en charge dans votre environnement Lync Server 2013, vous pouvez également spécifier une action par défaut pour les clients qui n’ont pas encore de stratégie de version définie. Cela vous permet de limiter les versions de client utilisées dans votre environnement Lync Server, ce qui vous permet de contrôler les coûts associés à la prise en charge de plusieurs versions du client.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>Pour modifier l’action par défaut des clients qui ne sont pas explicitement pris en charge ou restreints

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration de la version du client**.

4.  Dans la page **Configuration de la version du client**, double-cliquez sur la configuration **Global** dans la liste.

5.  Dans la boîte de dialogue **Modifier la configuration de la version du client**, vérifiez que la case à cocher **Activer le contrôle de version** est activée puis, sous **Action par défaut**, sélectionnez l’une des options suivantes :
    
      - **Autoriser**   : autorise le client à se connecter si sa version ne correspond à aucun filtre dans la liste des **stratégies de version du client** .
    
      - **Bloquer**   : empêche le client de se connecter si sa version ne correspond à aucun filtre dans la liste des **stratégies de version du client** .
    
      - **Bloquer avec une URL**   : empêche le client de se connecter si sa version ne correspond à aucun filtre dans la liste des **stratégies de version du client** , et inclut un message d’erreur contenant une URL dans laquelle un client plus récent peut être téléchargé.
    
      - **Allow with URL**   autorise le client à se connecter si la version du client ne correspond à aucun filtre dans la liste des **stratégies de version du client** , et inclut un message d’erreur contenant une URL dans laquelle un client plus récent peut être téléchargé.

6.  Si vous avez sélectionné **Bloquer avec une URL**, dans la zone **URL**, tapez l’URL de téléchargement du client à inclure dans le message d’erreur.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-disable-client-version-control"></a>Pour désactiver le contrôle de version des clients

  - Pour désactiver le contrôle de version afin d’autoriser tous les clients à se connecter quelle que soit leur version, désactivez la case à cocher **Activer le contrôle de version**, puis cliquez sur **Valider**.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Modification de l’action par défaut à l’aide des applets de commande Windows PowerShell

L’action par défaut à effectuer lorsque les utilisateurs essaient de se connecter à l’aide de clients qui ne sont pas explicitement pris en charge ou restreints par une stratégie de version de client peuvent être gérés à l’aide de l’interface de ligne de commande Windows PowerShell et de la cmdlet **Set-CsClientVersionPolicy** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>Pour configurer l’action par défaut pour bloquer l’accès

  - La commande suivante définit l’action par défaut du site Redmond à Block. Elle permet de bloquer l’inscription des clients pour lesquels il n’existe aucune règle de configuration des versions des clients.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>Pour configurer l’action par défaut pour autoriser l’accès

  - Dans cet exemple, l’action par défaut du site Redmond est définie à Allow. Cela permet d’autoriser l’inscription des clients pour lesquels il n’existe aucune règle de configuration des versions des clients.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion des appareils, des téléphones et des applications clientes dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

