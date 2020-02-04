---
title: 'Lync Server 2013 : activation ou désactivation de la suppression de données archivées'
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
ms.openlocfilehash: 3b06d21cc0154ea57bc028c87c835e4de9a00f1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Activation ou désactivation de la suppression de données archivées dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Dans Lync Server 2013 panneau de configuration, vous utilisez des configurations d’archivage pour activer et désactiver la purge et configurer le mode d’implémentation de la purge. Cela inclut les configurations d’archivage suivantes :

  - Configuration globale créée par défaut lors du déploiement de Lync Server 2013.

  - Configurations facultatives de niveau de site et de niveau groupe que vous pouvez créer et utiliser pour spécifier la façon dont l’archivage est implémenté pour des sites ou des groupes spécifiques.

Vous définissez initialement des configurations d’archivage lors du déploiement de l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement. Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou les opérations.

<div>


> [!NOTE]  
> Pour utiliser l’archivage pour les utilisateurs hébergés sur Lync Server 2013, vous devez configurer des stratégies d’archivage pour spécifier s’il convient d’activer l’archivage des communications internes, pour les communications externes ou pour les deux. Par défaut, l’archivage n’est pas activé pour les communications internes et externes. Avant l’activation de l’archivage dans toutes les stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, si vous le souhaitez, pour des sites et des groupes spécifiques, comme décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuration et affectation de stratégies d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.<BR>Si vous décidez après le déploiement de l’archivage dans lequel vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données et fichiers d’archivage sur les serveurs Exchange 2013 et que tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013, vous devez supprimer la configuration de la base de données SQL Server à partir de votre topologie. Pour ce faire, vous devez utiliser le générateur de topologie. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-changing-archiving-database-options.md">modifier les options de base de données d’archivage dans Lync Server 2013</A> dans la documentation sur les opérations



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>Pour activer ou désactiver la suppression définitive de l’archivage

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.

4.  Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, sur **Afficher les détails** et procédez comme suit :
    
      - Pour activer le vidage, activez la case à cocher **Activer le vidage des données d’archivage** et effectuez l’une des actions suivantes :
        
          - Pour vider tous les enregistrements, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
        
          - Pour ne purger que les données qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
      - Pour désactiver le vidage, désactivez la case à cocher **Activer le vidage des données d’archivage**.

5.  Cliquez sur **Valider**.

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la suppression de données d’archivage à l’aide d’applets de cmdlet Windows PowerShell

L’activation et la désactivation de la purge automatique des données d’archivage peuvent être gérées à l’aide de Windows PowerShell et de l’applet **de passe Set-CsArchivingConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>Pour activer la suppression de toutes les données d’archivage

  - Pour activer la suppression de toutes les données d’archivage, définissez la propriété **EnablePurging** sur true ($true). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Après avoir exécuté cette commande, chaque jour, le serveur Lync efface tous les enregistrements d’archivage antérieurs à la valeur spécifiée pour la propriété **KeepArchivingDataForDays** .

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>Pour activer la suppression des données d’archivage exportées uniquement

  - Pour limiter la suppression de l’archivage d’enregistrements qui ont été exportés dans un fichier de données (à l’aide de l’applet de cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), vous devez également définir la propriété PurgeExportedArchivesOnly sur True ($true). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Une fois la commande exécutée, le serveur Lync purge uniquement les enregistrements qui répondent aux deux critères suivants : 1) dont la valeur est antérieure à celle spécifiée pour la propriété **KeepArchivingDataForDays** . et 2) elles ont été exportées à l’aide de l’applet de passe **Export-CsArchivingData** .

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>Pour désactiver la suppression de toutes les données d’archivage

  - Pour désactiver la purge automatique des enregistrements d’archivage, définissez la propriété **EnablePurging** sur false ($false). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

Pour plus d’informations, y compris des options supplémentaires permettant de purger les données d’archivage, consultez la rubrique d’aide de l’applet de passe [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .

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

