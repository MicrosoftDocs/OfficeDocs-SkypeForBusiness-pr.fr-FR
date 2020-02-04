---
title: 'Lync Server 2013 : suppression d’une configuration de l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e4a0c1acf9f605fc927d7006ff50b1f4470c68d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a>Suppression d’une configuration d’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez supprimer une configuration de pool ou de configuration de site. La configuration globale ne peut pas être supprimée. Si vous supprimez la configuration globale, ses valeurs par défaut sont automatiquement rétablies. Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou les opérations.

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a>Pour supprimer une configuration de site ou de pool pour l’archivage

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.

4.  Dans la liste des configurations d’archivage, cliquez sur la configuration de site ou de pool que vous souhaitez supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.

5.  Cliquez sur **Valider**.

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>Supprimer les paramètres de configuration de l’archivage à l’aide des cmdlets Windows PowerShell

Vous pouvez supprimer des paramètres de configuration de l’archivage à l’aide de Windows PowerShell et de l’applet de passe **Remove-CsArchivingConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a>Pour supprimer une collection spécifiée de paramètres de configuration de l’archivage

  - La commande suivante supprime les paramètres de configuration de l’archivage appliqués au site de Redmond :
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration de l’archivage appliqués à l’étendue du site

  - Cette commande supprime tous les paramètres de configuration de l’archivage appliqués à l’étendue du service :
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a>Pour supprimer les paramètres de configuration de l’archivage en fonction d’une valeur de propriété spécifiée

  - Cette commande supprime tous les paramètres de configuration de l’archivage dans lesquels l’archivage Exchange a été désactivé :
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Gestion de l’archivage des communications internes et externes dans Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

