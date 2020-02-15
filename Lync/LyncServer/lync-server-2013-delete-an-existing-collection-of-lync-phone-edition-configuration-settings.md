---
title: Supprimer une collection existante de paramètres de configuration de Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 175f7d9cd5417f350dd08873aa748c56d829d86d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Supprimer une collection existante de paramètres de configuration Lync Phone Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Si vous ne souhaitez plus utiliser une collection de paramètres pour les appareils exécutant Lync Phone Edition, supprimez-le. Si vous supprimez la collection de paramètres d’un site, les paramètres globaux s’appliqueront aux téléphones de ce site. Vous ne pouvez pas supprimer la collection globale.

<div>


> [!NOTE]
> Au lieu de supprimer une collection, vous pouvez simplement modifier certains des paramètres. Pour plus d’informations sur la procédure à suivre, voir <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">créer ou modifier une collection de paramètres de configuration de Lync Phone Edition dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Pour supprimer une collection de paramètres de configuration de Lync Phone Edition

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration du périphérique**.

4.  Dans la page **Configuration du périphérique**, cliquez sur la collection à supprimer, sur le menu **Edition**, puis sur **Supprimer**.
    
    <div>
    

    > [!NOTE]
    > Si vous supprimez la collection globale, les paramètres par défaut sont simplement rétablis. La collection ne disparaît pas.

    
    </div>

5.  Dans la boîte de dialogue de confirmation, cliquez sur **OK**.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration de Lync Phone Edition à l’aide des applets de commande Windows PowerShell

Vous pouvez supprimer les paramètres de configuration de Lync Phone Edition à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsUCConfiguration** . Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>Pour supprimer une collection spécifique de paramètres de configuration de Lync Phone Edition

  - Cette commande permet de supprimer les paramètres de configuration du téléphone pour messagerie unifiée appliqués au site Redmond :
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration de Lync Phone Edition appliqués à l’étendue site

  - Cette commande permet de supprimer tous les paramètres de configuration du téléphone pour messagerie unifiée appliqués à l’étendue Service :
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>Pour supprimer tous les paramètres de configuration de Lync Phone Edition où le verrouillage du téléphone est désactivé

  - Cette commande permet de supprimer les collections de paramètres de configuration du téléphone pour messagerie unifiée dans lesquels le verrouillage du téléphone a été désactivé :
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

Pour plus d’informations, consultez la rubrique [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).

</div>

</div>

<span> </span>

</div>

</div>

</div>

