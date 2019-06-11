---
title: Modifier l’action par défaut pour les clients non explicitement pris en charge ou limités
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b364253a87f1cbff1ef60322c65780b6497880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Modifier l’action par défaut pour les clients non explicitement pris en charge ou limités dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

En plus de spécifier la version de clients que vous voulez prendre en charge dans votre environnement Lync Server 2013, vous pouvez également spécifier une action par défaut pour les clients qui ne disposent pas encore d’une stratégie de version définie. Cela vous permet de limiter les versions de client utilisées dans votre environnement Lync Server, qui peuvent vous aider à contrôler les coûts associés à la prise en charge de plusieurs versions de clients.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>Pour modifier l’action par défaut pour les clients non explicitement pris en charge ou limités

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **clients**, puis sur Configuration de la **version du client**.

4.  Dans la page Configuration de la **version du client** , double-cliquez sur la configuration **globale** dans la liste.

5.  Dans la boîte de dialogue **modifier la configuration de version du client** , assurez-vous que la case à cocher Activer le contrôle de **version** est activée, puis, sous **action par défaut**, sélectionnez l’une des options suivantes:
    
      - **Autoriser**   autorise le client à se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la **version du client** .
    
      - **Bloquer**   empêche le client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la **version du client** .
    
      - **Bloquer avec une URL**   empêche le client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la **version du client** , et qu’il inclut un message d’erreur contenant une URL dans laquelle un client plus récent peut être téléchargé.
    
      - **Allow with URL**   autorise le client à se connecter si la version du client ne correspond à aucun filtre figurant dans la liste des stratégies de la **version du client** , et qu’il s’agit d’un message d’erreur contenant une URL indiquant qu’un client plus récent peut être téléchargé.

6.  Si vous avez sélectionné **bloquer avec une URL**, tapez l’URL de téléchargement du client à inclure dans le message d’erreur dans la zone **URL** .

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-disable-client-version-control"></a>Pour désactiver le contrôle de version du client

  - Pour désactiver le contrôle de version afin de permettre à tous les clients de se connecter quelle que soit la version du client, désactivez la case à cocher **activer le contrôle de version** , puis cliquez sur **valider**.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Modification de l’action par défaut à l’aide des cmdlets Windows PowerShell

L’action par défaut à effectuer lorsque les utilisateurs essaient de se connecter à l’aide de clients qui ne sont pas explicitement pris en charge ou limités par une stratégie de version du client peuvent être gérés à l’aide de l’interface de ligne de commande Windows PowerShell et de l’applet **de commande Set-CsClientVersionPolicy** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>Pour configurer l’action par défaut pour bloquer l’accès

  - La commande suivante définit l’action par défaut pour le bloc de site Redmond. Tout client pour lequel aucune règle de configuration de la version client n’existe.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>Pour configurer l’action par défaut pour autoriser l’accès

  - Dans cet exemple, l’action par défaut du site Redmond est définie sur autoriser. Cela permettra une inscription pour les clients pour lesquels il n’existe aucune règle de configuration de version de client.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

