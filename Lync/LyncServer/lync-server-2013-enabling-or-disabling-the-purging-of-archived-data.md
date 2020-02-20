---
title: 'Lync Server 2013 : activation ou désactivation de la purge des données archivées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d8ee7858e339029fa29c803400ac836871515b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Activation ou désactivation de la purge des données archivées dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Dans le panneau de configuration Lync Server 2013, vous utilisez des configurations d’archivage pour activer et désactiver le vidage et configurer la mise en œuvre de la purge. Les configurations d’archivage sont les suivantes :

  - Une configuration globale qui est créée par défaut lorsque vous déployez Lync Server 2013.

  - Configurations facultatives au niveau du site et au niveau du pool que vous pouvez créer et utiliser pour spécifier la manière d’implémenter l’archivage de sites ou de pools spécifiques.

Vous commencez par définir des configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations à l’issue du déploiement. Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

<div>


> [!NOTE]  
> Pour utiliser l’archivage pour les utilisateurs hébergés sur Lync Server 2013, vous devez configurer des stratégies d’archivage pour spécifier s’il faut activer l’archivage pour les communications internes, pour les communications externes ou pour les deux. Par défaut, l’archivage n’est pas activé pour les communications internes ou externes. Avant d’activer l’archivage dans une stratégie, vous devez spécifier les configurations d’archivage adéquates pour votre déploiement et, éventuellement, pour des sites et des pools spécifiques, comme cela est décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving Policies in Lync Server 2013</A> dans la documentation de déploiement.<BR>Si vous décidez après avoir déployé l’archivage dans lequel vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données d’archivage et les fichiers sur les serveurs Exchange 2013 et que tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013, vous devez supprimer la configuration de la base de données SQL Server. à partir de votre topologie. Pour ce faire, vous devez utiliser le générateur de topologie. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving Database options in Lync Server 2013</A> dans la documentation des opérations.



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>Pour activer ou désactiver le vidage de l’archivage

1.  À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.

4.  Cliquez sur le nom de la configuration appropriée (globale, du site ou du pool) dans la liste des configurations d’archivage, cliquez sur **Modifier**, sur **Afficher les détails**, puis procédez comme suit :
    
      - Pour activer le vidage, activez la case à cocher **Activer le vidage des données d’archivage** et effectuez l’une des actions suivantes :
        
          - Pour vider tous les enregistrements, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
        
          - Pour ne purger que les données qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
      - Pour désactiver le vidage, désactivez la case à cocher **Activer le vidage des données d’archivage**.

5.  Cliquez sur **Valider**.

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la purge des données d’archivage à l’aide des applets de commande Windows PowerShell

L’activation et la désactivation de la purge automatisée des données d’archivage peuvent être gérées à l’aide de Windows PowerShell et de la cmdlet **Set-applet csarchivingconfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>Pour activer le vidage de toutes les données d’archivage

  - Pour activer le vidage de toutes les données d’archivage, définissez la propriété **EnablePurging** sur true ($True). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Une fois cette commande exécutée, Lync Server purge tous les enregistrements d’archivage antérieurs à la valeur spécifiée pour la propriété **KeepArchivingDataForDays** .

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>Pour activer la purge uniquement des données d’archivage exportées

  - Pour limiter la purge aux enregistrements d’archivage qui ont été exportés vers un fichier de données (à l’aide de la cmdlet [Export-applet csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), vous devez également définir la propriété PurgeExportedArchivesOnly sur True ($true). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Une fois cette commande exécutée, Lync Server n’efface que les enregistrements d’archivage qui répondent à deux critères : 1) ils sont plus anciens que la valeur spécifiée pour la propriété **KeepArchivingDataForDays** ; et, 2) qu’ils ont été exportés à l’aide de la cmdlet **Export-applet csarchivingdata** .

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>Pour désactiver le vidage de toutes les données d’archivage

  - Pour désactiver le vidage automatique des enregistrements d’archivage, définissez la propriété **EnablePurging** sur False ($False). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

Pour plus d’informations, y compris des options supplémentaires pour purger les données d’archivage, voir la rubrique d’aide relative à la cmdlet [Set-applet csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Configuration et affectation de stratégies d’archivage dans Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

