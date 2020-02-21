---
title: 'Lync Server 2013 : création ou modification d’une stratégie de version de client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e95abe52883bff2c99ad02b01ea4cc1473f4626f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>Création ou modification d’une nouvelle stratégie de version du client dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez utiliser les stratégies de version du client pour spécifier les versions des clients prises en charge dans votre environnement. L’utilisation du contrôle de version du client permet de réduire les coûts associés à la prise en charge de plusieurs versions du client. Elle peut également améliorer l’expérience globale de l’utilisateur, car lorsque des versions antérieures et ultérieures de clients interagissent, les fonctionnalités disponibles peuvent être limitées par la version antérieure du client. Vous pouvez créer ou modifier des stratégies de version des clients à partir du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>Pour créer ou modifier des stratégies de version des clients à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**.
    
    <div>
    

    > [!NOTE]  
    > L’onglet <STRONG>Stratégie de version du client</STRONG> est sélectionné par défaut.

    
    </div>

4.  Sur la page **stratégie de version du client** , effectuez l’une des opérations suivantes :
    
      - Pour créer une stratégie de version de client, cliquez sur **nouveau**, sélectionnez **stratégie de site**, **stratégie de pool**ou **stratégie utilisateur**, puis cliquez sur **OK**.
    
      - Pour modifier la stratégie globale ou une autre stratégie de version de client existante, sélectionnez la stratégie, cliquez sur **modifier**, puis sur **afficher les détails**.

5.  Sur la page **modifier la stratégie de version du client** , créez ou modifiez des règles comme décrit dans [créer ou modifier une règle de stratégie de version des clients dans Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>Création ou modification des stratégies de version des clients à l’aide des applets de commande Windows PowerShell

Vous pouvez créer des stratégies de version du client à l’aide de la cmdlet **New-CsClientVersionPolicy** et les modifier à l’aide de la cmdlet **Set-CsClientVersionPolicy** . Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>Pour créer une stratégie de version de client étendue site

  - La commande suivante crée une stratégie de version de client appliquée au site Redmond. Étant donné qu’aucun paramètre supplémentaire n’est spécifié, la nouvelle stratégie utilisera les paramètres de version du client par défaut.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>Pour créer une stratégie de version de client par utilisateur

  - Pour créer une stratégie par utilisateur, utilisez une commande semblable à celle-ci :
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

Pour plus d’informations, reportez-vous aux rubriques d’aide pour la cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) et la cmdlet [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

