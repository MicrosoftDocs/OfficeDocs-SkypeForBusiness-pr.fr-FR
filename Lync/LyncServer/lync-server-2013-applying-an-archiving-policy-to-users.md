---
title: 'Lync Server 2013: application d’une stratégie d’archivage aux utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56bb6705187172888c9fdac33532e25a210e8246
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Appliquer une stratégie d’archivage aux utilisateurs de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Si un utilisateur a été activé pour Lync Server 2013 et que vous avez créé une ou plusieurs stratégies utilisateur pour l’archivage pour les utilisateurs hébergés sur Lync Server 2013, vous pouvez implémenter la prise en charge de l’archivage pour des utilisateurs spécifiques en appliquant les stratégies appropriées aux utilisateurs ou groupes d’utilisateurs. Par exemple, si vous créez une stratégie pour la prise en charge de l’archivage des communications internes, vous pouvez l’appliquer à au moins un utilisateur ou groupe d’utilisateurs pour la prise en charge de l’archivage des communications Lync Server 2013 de l’utilisateur.

<div>


> [!NOTE]  
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, Exchange stratégies de conservation inaltérable Déterminez si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées sur le blocage sur place. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuration de stratégies d’archivage dans Lync server 2013 lors de l’utilisation d’une intégration Exchange Server</A> dans la documentation de déploiement.<BR>Vous devez spécifier toutes les options appropriées dans les configurations d’archivage avant de procéder à l’archivage. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">la section gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</A> dans la documentation des opérations.



</div>

Suivez la procédure décrite dans cette rubrique pour appliquer une stratégie utilisateur d’archivage déjà créée à un ou plusieurs comptes d’utilisateurs ou groupes d’utilisateurs.

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>Pour appliquer une stratégie utilisateur d’archivage à un compte d’utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **modifier l’utilisateur de Lync Server** sous **stratégie**d’archivage, sélectionnez la stratégie d’utilisateur d’archivage que vous voulez appliquer.
    
    <div>
    

    > [!NOTE]  
    > Les <STRONG> &lt;paramètres&gt; automatiques</STRONG> appliquent les paramètres d’installation du serveur par défaut. Ces paramètres sont appliqués automatiquement par le serveur.

    
    </div>

6.  Cliquez sur **Valider**.

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Attribution d’une stratégie d’archivage par utilisateur à l’aide des applets de cmdlet Windows PowerShell

Les stratégies d’archivage par utilisateur peuvent être affectées à l’aide de Windows PowerShell et de l’applet **de passe Grant-CsArchivingPolicy** . Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Pour attribuer une stratégie d’archivage par utilisateur à un utilisateur unique

  - La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Pour attribuer une stratégie d’archivage par utilisateur à plusieurs utilisateurs

  - Cette commande affecte le RedmondArchivingPolicy de stratégie d’archivage par utilisateur à tous les utilisateurs disposant de comptes hébergés sur le pool d’inscriptions atl-cs-001.litwareinc.com. Pour plus d’informations sur le paramètre de filtre utilisé dans cette commande, consultez la documentation sur l’applet de commande [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>Pour attribuer une stratégie d’archivage par utilisateur

  - La commande suivante réattribue toutes les stratégies d’archivage par utilisateur précédemment affectées à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Pour plus d’informations, reportez-vous à la documentation sur l’applet [de passe Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion de l’archivage des communications internes et externes dans Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

