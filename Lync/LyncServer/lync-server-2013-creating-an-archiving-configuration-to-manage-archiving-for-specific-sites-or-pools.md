---
title: 'Lync Server 2013 : création d’une configuration d’archivage pour gérer l’archivage de sites ou de pools spécifiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c23afb99e20e8e23582664568eba4fb0b7b841
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a>Création d’une configuration d’archivage dans Lync Server 2013 pour gérer l’archivage de sites ou de pools spécifiques

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Dans le panneau de configuration Lync Server 2013, vous utilisez des configurations d’archivage pour contrôler l’implémentation de l’archivage dans votre déploiement. Les configurations d’archivage sont les suivantes :

  - Une configuration globale qui est créée par défaut lorsque vous déployez Lync Server 2013.

  - Configurations facultatives au niveau du site et au niveau du pool que vous pouvez créer et utiliser pour spécifier la manière d’implémenter l’archivage de sites ou de pools spécifiques.

Vous commencez par définir des configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations à l’issue du déploiement. Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

<div>


> [!NOTE]  
> Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage pour spécifier s’il faut activer l’archivage pour les communications internes, pour les communications externes ou pour les deux pour les utilisateurs hébergés sur Lync Server 2013. Par défaut, l’archivage n’est pas activé pour les communications internes ou externes. Avant d’activer l’archivage dans des stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, éventuellement, pour des sites et pools spécifiques, comme décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving Policies in Lync Server 2013</A> dans la documentation de déploiement.<BR>Si vous décidez après avoir déployé l’archivage dans lequel vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données d’archivage et les fichiers sur les serveurs Exchange 2013 et que tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013, vous devez supprimer la configuration de la base de données SQL Server. à partir de votre topologie. Pour ce faire, vous devez utiliser le générateur de topologie. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving Database options in Lync Server 2013</A> dans la documentation des opérations.



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a>Pour créer une configuration d’archivage pour un site ou un pool

1.  À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.

4.  Dans la page **configuration de l’archivage** , cliquez sur **nouveau**, puis effectuez l’une des opérations suivantes :
    
      - Pour créer une configuration d’archivage de site, cliquez sur **configuration du site** puis, dans **Sélectionner un site**, sélectionnez le site à configurer pour l’archivage.
    
      - Pour créer une configuration d’archivage de pool, cliquez sur **configuration du pool** , puis, dans **Sélectionner un pool**, sélectionnez le pool à configurer pour l’archivage.

5.  Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :
    
      - Afin d’activer l’archivage uniquement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
      - Pour activer l’archivage pour les sessions de messagerie instantanée et les conférences Web, cliquez sur **archiver les sessions de messagerie instantanée et de conférence Web**.
    
      - Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.

6.  Dans **Créer un paramètre d’archivage**, procédez comme suit :
    
      - Pour bloquer toute activité quand l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
      - Pour utiliser Microsoft Exchange Server afin de stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .
    
      - Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
        
          - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.
        
          - Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création de paramètres de configuration d’archivage à l’aide d’applets de commande Windows PowerShell

Les paramètres de configuration de l’archivage peuvent être créés à l’aide de Windows PowerShell et de la cmdlet New-applet csarchivingconfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a>Pour créer une nouvelle collection de paramètres de configuration d’archivage pour un site

  - La commande suivante crée une nouvelle collection de paramètres de configuration d’archivage pour le site Redmond :
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a>Pour créer une nouvelle collection de paramètres de configuration d’archivage qui autorise uniquement l’archivage de la messagerie instantanée

  - Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui font appel à d’autres valeurs de propriétés, incluez simplement le paramètre approprié et sa valeur. Par exemple, pour créer une collection de paramètres de configuration d’archivage qui, par défaut, autorise l’archivage des sessions de messagerie instantanée, utilisez uniquement une commande comme celle-ci :
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a>Pour spécifier plusieurs valeurs de propriétés lors de la création des paramètres de configuration d’archivage

  - Plusieurs valeurs de propriété peuvent être modifiées en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres pour archiver les sessions de messagerie instantanée et bloquer la messagerie instantanée du service d’archivage n’est pas disponible :
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet [New-applet csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

