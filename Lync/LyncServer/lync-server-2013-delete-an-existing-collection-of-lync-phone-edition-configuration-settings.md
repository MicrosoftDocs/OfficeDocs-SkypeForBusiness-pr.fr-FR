---
title: Supprimer une collection existante de paramètres de configuration de Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2be234fdbb2beb9d2f6f038acbdad03dd8d2048
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Supprimer une collection existante de paramètres de configuration de Lync Phone Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Si vous ne voulez plus utiliser un ensemble de paramètres pour les appareils exécutant Lync Phone Edition, supprimez-le. Si vous supprimez une collection pour un site, les paramètres globaux s’appliquent aux téléphones de ce site. Vous ne pouvez pas supprimer la collection globale.

<div>


> [!NOTE]
> Au lieu de supprimer une collection, il est possible que vous vouliez simplement modifier certains paramètres. Pour plus d’informations sur la façon de procéder, voir <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">créer ou modifier un ensemble de paramètres de configuration de Lync Phone Edition dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Pour supprimer une collection de paramètres de configuration de Lync Phone Edition

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton navigation de **configuration d’appareil** .

4.  Dans la page Configuration de l' **appareil** , cliquez sur la collection que vous voulez supprimer, cliquez sur le menu **modifier** , puis cliquez sur **supprimer**.
    
    <div>
    

    > [!NOTE]
    > Si vous supprimez la collection globale, les paramètres sont restaurés par défaut. La collection n’est pas déplacée.

    
    </div>

5.  Dans la boîte de confirmation, cliquez sur **OK**.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Supprimer les paramètres de configuration de Lync Phone Edition en utilisant des applets de cmdlet Windows PowerShell

Vous pouvez supprimer des paramètres de configuration de Lync Phone Edition à l’aide de Windows PowerShell et de l’applet de passe **Remove-CsUCConfiguration** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>Pour supprimer une collection de paramètres de configuration de Lync Phone Edition spécifiée

  - Cette commande supprime les paramètres de configuration de téléphone UC appliqués au site de Redmond:
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration de Lync Phone Edition appliqués à l’étendue du site

  - Cette commande supprime tous les paramètres de configuration de téléphone de UC appliqués à l’étendue du service:
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>Pour supprimer tous les paramètres de configuration de Lync Phone Edition dans lesquels le verrouillage de téléphone est désactivé

  - Cette commande supprime tous les ensembles de paramètres de configuration du téléphone de type UC pour lesquels le verrouillage du téléphone a été désactivé:
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

Pour plus d’informations, consultez la rubrique [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).

</div>

</div>

<span> </span>

</div>

</div>

</div>

