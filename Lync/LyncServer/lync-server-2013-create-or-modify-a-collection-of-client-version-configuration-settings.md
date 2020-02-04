---
title: Créer ou modifier un ensemble de paramètres de configuration de la version du client
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
ms.openlocfilehash: 7fc50696444ddd0602bbf21fd9e05b5bba6eddde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Créer ou modifier un ensemble de paramètres de configuration de la version du client dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client. La configuration de la version du client global s’installe sur Lync Server et est utilisée pour activer ou désactiver le contrôle de version du client pour le déploiement complet du serveur. Vous pouvez également configurer les paramètres de configuration de la version du client pour chaque site. Vous pouvez créer ou modifier les paramètres de configuration de la version du client à partir du panneau de configuration de Lync Server 2013 ou de Lync Server 2013 Management Shell.

<div>


> [!NOTE]
> Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes ne sont affectés que par les stratégies globales.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Pour créer ou modifier les paramètres de configuration de la version du client à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation configuration de la **version du client** .

4.  Dans la page Configuration de la **version du client** , procédez comme suit :
    
      - Pour créer une nouvelle configuration, cliquez sur **nouveau**, sélectionnez un site, cliquez **sur nom de** l’utilisateur et mettez à jour les paramètres.
    
      - Pour modifier une configuration, sélectionnez celle-ci, cliquez sur **modifier**, sur **afficher les détails**, puis apportez les modifications souhaitées aux paramètres.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création ou modification des paramètres de configuration de la version du client à l’aide des cmdlets Windows PowerShell

Vous pouvez créer des paramètres de configuration de la version du client à l’aide de l’applet **de nouvelle cmdlet New-CsClientVersionConfiguration** et les modifier à l’aide de l’applet de contrôle **Set-CsClientVersionConfiguration** . Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>Pour créer une nouvelle collection de paramètres de configuration de la version du client

  - La commande suivante crée une nouvelle collection de paramètres de configuration de la version du client appliqués au site de Redmond. Dans cet exemple, le contrôle de version du client est désactivé pour le site de Redmond.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>Pour activer le contrôle de version du client pour un site

  - Cette commande autorise le contrôle de version du client pour le site de Redmond.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>Pour désactiver le contrôle de version du client au sein de l’Organisation

  - Dans cet exemple, le contrôle de version du client est désactivé pour tous les paramètres de configuration de la version du client utilisés au sein de l’organisation.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

Pour plus d’informations, consultez la rubrique d’aide pour les applets de [nouvelle-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) et [Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

