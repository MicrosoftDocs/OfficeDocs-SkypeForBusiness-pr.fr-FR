---
title: Créer ou modifier une collection de paramètres de configuration de la version du client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56061b4d6c801263c30e471acef70e68c10bfea1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521741"
---
# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Création ou modification d’une collection de paramètres de configuration de la version du client dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client. La configuration de la version du client globale s’installe avec Lync Server et est utilisée pour activer ou désactiver le contrôle de version du client pour l’ensemble du déploiement du serveur. Vous pouvez également configurer les paramètres de configuration de la version du client pour des sites individuels. Vous pouvez créer ou modifier les paramètres de configuration de la version du client à partir du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

<div>


> [!NOTE]
> Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Pour créer ou modifier des paramètres de configuration de la version du client à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation configuration de la **version du client** .

4.  Sur la page Configuration de la **version du client** , procédez comme suit :
    
      - Pour créer une nouvelle configuration, cliquez sur **nouveau**, sélectionnez un site, cliquez sur **OK** , puis mettez à jour les paramètres.
    
      - Pour modifier une configuration, sélectionnez la configuration, cliquez sur **modifier**, sur **afficher les détails**, puis apportez des modifications aux paramètres.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création ou modification des paramètres de configuration de la version du client à l’aide des applets de commande Windows PowerShell

Vous pouvez créer des paramètres de configuration de version des clients à l’aide de la cmdlet **New-CsClientVersionConfiguration** et les modifier à l’aide de l’applet de commande **Set-CsClientVersionConfiguration** . Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>Pour créer une nouvelle collection de paramètres de configuration de la version du client

  - La commande suivante crée une nouvelle collection de paramètres de configuration de la version du client appliqués au site de Redmond. Dans cet exemple, le contrôle de version du client est désactivé pour le site de Redmond.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>Pour activer le contrôle de version du client pour un site

  - Cette commande active le contrôle de version du client pour le site de Redmond.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>Pour désactiver la gestion des versions du client au sein de l’Organisation

  - Dans cet exemple, le contrôle de version du client est désactivé pour tous les paramètres de configuration de la version du client utilisés dans l’organisation.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

Pour plus d’informations, consultez la rubrique d’aide relative aux applets de commande [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) et [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

