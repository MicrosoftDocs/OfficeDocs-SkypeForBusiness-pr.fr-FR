---
title: 'Lync Server 2013 : autorisations et conditions préalables pour la configuration du groupe Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7289b8818a6193efa867ab0a8671abf6d4701f7c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511741"
---
# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Autorisations et conditions préalables à la configuration du groupe Response Group dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Response Group est une fonctionnalité de gestion des appels de Voix Entreprise. Cette rubrique décrit la configuration dont vous avez besoin avant de pouvoir configurer Response Group et les autorisations et informations d’identification d’administrateur nécessaires pour effectuer les tâches de configuration.

Cette section présuppose que vous avez lu la documentation de planification relative à Response Group. Pour plus d’informations, reportez-vous à la rubrique [Planning for Call Management Features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) dans la documentation de planification.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>Outils de configuration et rôles d’administrateur

Vous pouvez utiliser les outils d’administrateur suivants pour configurer Response Group :

  - Panneau de commande Lync Server

  - outil de configuration Response Group

  - Lync Server Management Shell

Pour configurer les groupes Response Group, vous devez être membre d’au moins un des rôles d’administrateur suivants :


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Groupe de sécurité Active Directory (1)</strong></p></td>
<td><p>Créer un flux de travail</p></td>
<td><p>Assigner un responsable</p></td>
<td><p>Créer/assigner des agents, files d’attente</p></td>
<td><p>Créer/gérer des vacances et heures d’ouverture</p></td>
<td><p>Activer/désactiver un flux de travail</p></td>
<td><p>Configurer un flux de travail (réponse vocale interactive ou groupe de recherche)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>√ (2)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> un objet utilisateur des services de domaine Active Directory doit être membre du groupe de sécurité Active Directory spécifié. Un administrateur ou un membre d’un groupe Active Directory délégué doté des autorisations appropriées pour ajouter des utilisateurs à un groupe de sécurité (par exemple, administrateur, opérateurs de compte) doit ajouter un objet utilisateur au groupe ou au groupe de sécurité indiqué pour que l’utilisateur puisse exécuter les fonctions indiquées. <STRONG>(2)</STRONG> uniquement pour les flux de travail que l’CsResponseGroupAdministrator a affectées à l’CsResponseGroupManager. <STRONG>(3)</STRONG> un responsable Response Group peut attribuer un autre membre de CsResponseGroupManager à un flux de travail que le responsable actuel gère déjà. <STRONG>(4)</STRONG> CsViewOnlyAdministrator ne peut exécuter que les cmdlets « Get » de Lync Server Management Shell.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>Conditions préalables à la configuration de Response Group

Response Group requiert les composants suivants :

  - Service d’application

  - Application Response Group

  - Modules linguistiques

  - Magasin de fichiers (pour conserver les fichiers audio)

  - Services Web (inclut l’outil de configuration Response Group et la console de connexion et de déconnexion des agents)

Tous ces composants sont installés par défaut lorsque vous déployez Voix Entreprise.

Vous devrez peut-être effectuer les tâches suivantes avant de configurer Response Group :

  - Activez les utilisateurs pour Lync Server 2013 et voix entreprise.

  - modifier un fichier de configuration pour être compatible avec les normes FIPS (Federal Information Processing Standard) ;

  - modifier le classement de base de données afin de prendre en charge les caractères Yi, Meng et Zang pour les noms des files d’attente et des groupes d’agents.

<div>

## <a name="enabling-users"></a>Activation des utilisateurs

La première étape de la configuration du groupe Response Group consiste à créer des groupes d’agents. Avant de pouvoir créer un groupe d’agents, vous devez activer les utilisateurs qui seront agents pour Response Group pour Lync Server 2013 et voix entreprise. L’activation des utilisateurs pour Lync Server 2013 est généralement une étape dans le déploiement du serveur Enterprise Edition ou Standard Edition. Pour plus d’informations sur l’activation des utilisateurs pour Lync Server 2013, reportez-vous à la rubrique désactiver ou réactiver [le compte d’utilisateur pour Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). L’activation des utilisateurs pour Voix Entreprise se déroule généralement lors d’une étape du déploiement de Voix Entreprise. Pour plus d’informations, consultez la rubrique [activation des utilisateurs pour voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

</div>

<div>

## <a name="complying-with-fips-requirements"></a>Respect des normes FIPS

Cette section vous est applicable uniquement si votre entreprise doit se conformer aux normes FIPS (Federal Information Processing Standard).

Pour permettre une compatibilité avec la norme FIPS, vous devez modifier le fichier d’application Web.config afin d’utiliser un algorithme de chiffrement différent après l’installation des services web. Vous devez préciser le recours à l’algorithme de chiffrement triple 3DES (Triple Data Encryption Standard) pour qu’ASP.NET puisse traiter les données ViewState. Pour l’application Response Group, cette exigence s’applique à l’outil de configuration Response Group et à la console de connexion et de déconnexion de l’agent. Pour plus d’informations sur cette exigence, consultez l’article 911722 de la base de connaissances Microsoft, « vous pouvez recevoir un message d’erreur lorsque vous accédez à des pages Web ASP.NET dont le ViewState est activé après avoir effectué la mise à niveau de ASP.NET 1,1 vers ASP.NET 2,0 » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183) .

Pour modifier le fichier Web.config, procédez comme suit :

1.  Dans un éditeur de texte tel que le Bloc-Notes, ouvrez le fichier d’application Web.config.

2.  Dans le fichier Web.config, recherchez la `<system.web>` section.

3.  Ajoutez la `<machineKey>` section suivante à la `<system.web>` section :
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Enregistrez le fichier Web.config.

5.  Redémarrez le service IIS (Internet Information Services) en exécutant la commande suivante à une invite de commandes :
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Prise en charge des caractères Yi, Meng et Zang

Cette section vous est applicable seulement si votre organisation doit prendre en charge les caractères Yi, Meng ou Zang.

<div>


> [!NOTE]  
> Pour plus d’informations sur les caractères Yi, Meng et Zang et la raison pour laquelle ils peuvent être importants pour votre déploiement, consultez les informations sur les jeux de caractères GB18030 <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A> .



</div>

Pour la prise en charge des caractères Yi, Meng ou Zang, vous devez modifier le classement de la base de données Rgsconfig. Modifiez le classement de la colonne **Nom** des tableaux suivants dans chaque base de données Rgsconfig :

  - dbo. AgentGroups

  - dbo. BusinessHours

  - dbo. HolidaySets

  - dbo. Files d’attente

  - dbo. Travail

Pour SQL Server 2008 R2 et SQL Server 2012, utilisez le \_ classement latin général \_ 100 (accentué). Si vous utilisez ce classement, tous les noms d’objets ne tiennent pas compte de la casse.

Vous pouvez modifier le classement à l’aide de Microsoft SQL Server Management Studio. Pour plus d’informations sur l’utilisation de cet outil, voir « utilisation de SQL Server Management Studio » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184) . Pour modifier le classement, procédez comme suit :

1.  Assurez-vous que SQL Server Management Studio est configuré pour autoriser les modifications nécessaires à la recréation des tables. Pour plus d’informations, consultez la section « enregistrer (non autorisé) » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186) . Pour plus d’informations sur la définition d’un classement de colonne, voir « How to : Set Column collation (Visual Database Tools) » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185) .

2.  À l’aide de Microsoft SQL Server Management Studio, connectez-vous à la base de données Rgsconfig.

3.  Recherchez la table à modifier dans la base de données Rgsconfig, cliquez avec le bouton droit sur la table et cliquez sur **Conception**.

4.  Modifiez le classement de la colonne **Nom** et enregistrez la table.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

