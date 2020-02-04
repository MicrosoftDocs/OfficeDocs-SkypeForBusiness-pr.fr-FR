---
title: 'Lync Server 2013 : Préparation des services de domaine Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8abab29930e8b09d0642c84f1e02026d4c554637
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Préparation des services de domaine Active Directory dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-19_

Dans Lync Server 2013, vous pouvez utiliser l’Assistant Déploiement de Lync Server pour préparer les services de domaine Active Directory, ou vous pouvez utiliser les applets de cmdlet Lync Server Management Shell directement. Vous pouvez également utiliser l’outil de ligne de commande LDIFDE. exe directement sur vos contrôleurs de domaine, tel que décrit plus loin dans cette rubrique.

L’Assistant Déploiement de Lync Server vous guide à travers chaque tâche de préparation d’Active Directory. L’Assistant Déploiement exécute les applets de cmdlet Lync Server Management Shell. Cet outil est utile pour les environnements dotés d’une topologie de domaine unique et de forêt unique ou d’une autre topologie similaire.

<div>


> [!IMPORTANT]  
> Vous pouvez déployer Lync Server dans une forêt ou un domaine où les contrôleurs de domaine exécutent des versions 32 bits de certains systèmes d’exploitation (pour plus d’informations, voir <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Configuration requise pour l’infrastructure Active Directory pour Lync Server 2013</A>). Toutefois, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour exécuter une préparation de schéma, de forêt et de domaine dans ces environnements, car l’Assistant Déploiement et les fichiers de prise en charge sont uniquement de la 64. Au lieu de cela, vous pouvez utiliser Ldifde. exe et les fichiers. ldf associés sur un contrôleur de domaine 32 bits pour préparer le schéma, la forêt et le domaine. Voir la section « utilisation des cmdlets et LDIFDE. exe » plus loin dans cette rubrique.



</div>

Vous pouvez utiliser les applets de commande Lync Server Management Shell pour effectuer des tâches à distance ou pour des environnements plus complexes.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Conditions préalables à la préparation d’Active Directory

Vous devez exécuter les étapes de préparation d’Active Directory sur un ordinateur exécutant Windows Server 2012, Windows Server 2012 R2 ou Windows Server 2008 R2 avec SP1 (64-bit). La préparation d’Active Directory nécessite Lync Server Management Shell et OCSCore.

Les composants suivants sont nécessaires à l’exécution des tâches de préparation d’Active Directory :

  - Composants principaux de Lync Server (OCScore. msi)
    
    <div>
    

    > [!NOTE]  
    > Si vous envisagez d’utiliser Lync Server Management Shell pour la préparation d’Active Directory, vous devez d’abord exécuter l’Assistant Déploiement de Lync Server pour installer les composants principaux.

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Pour Windows Server 2012 et Windows Server 2012 R2, vous installez et activez .NET Framework 4,5 à l’aide du gestionnaire de serveur. Pour plus d’informations, 4,5 consultez la <A href="lync-server-2013-additional-software-requirements.md">configuration logicielle requise pour Lync Server 2013</A>. Pour Windows Server&nbsp;2008&nbsp;R2, téléchargez et installez <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.NET Framework 4,5</A> à partir du site Web Microsoft.

    
    </div>

  - Outils d’administration de serveur distant (RSAT)
    
    <div>
    

    > [!NOTE]  
    > Certains outils de RSAT sont requis si vous exécutez les étapes de préparation d’Active Directory sur un serveur membre plutôt que sur un contrôleur de domaine. Installez les composants logiciels enfichables et les outils de ligne de commande AD DS et le module Active Directory pour Windows PowerShell à partir du nœud AD DS et des outils AD LDS dans le gestionnaire de serveur.

    
    </div>

  - Microsoft Visual C++ 11 redistribuable
    
    <div>
    

    > [!NOTE]  
    > Le programme d’installation vous invite à installer cette configuration requise s’il n’est pas déjà installé sur l’ordinateur. Le package est fourni pour vous, et vous n’avez pas besoin de l’acquérir séparément.

    
    </div>

  - Windows PowerShell 3,0 (64 bits)
    
    Pour Windows Server 2012 et Windows Server 2012 R2, Windows PowerShell 3,0 doit être inclus avec votre installation de Lync Server 2013. Pour Windows Server 2008 R2, vous devez installer ou effectuer une mise à niveau vers Windows PowerShell 3,0. Pour plus d’informations, voir [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>Droits d’administrateur et rôles

Le tableau suivant répertorie les droits d’administration et les rôles requis pour chaque tâche de préparation Active Directory.

### <a name="user-rights-required-for-active-directory-preparation"></a>Droits d’utilisateur requis pour la préparation d’Active Directory

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Intérieur</th>
<th>Droits ou rôles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Préparation d’un schéma</p></td>
<td><p>Membre du groupe administrateurs de schéma pour le domaine racine de la forêt et les droits d’administrateur sur le maître de schéma</p></td>
</tr>
<tr class="even">
<td><p>Préparation d’une forêt</p></td>
<td><p>Membre du groupe administrateurs d’entreprise pour la forêt</p></td>
</tr>
<tr class="odd">
<td><p>Préparation d’un domaine</p></td>
<td><p>Membre du groupe administrateurs d’entreprise ou administrateurs de domaine pour le domaine spécifié</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Cmdlets de préparation Active Directory

Le tableau suivant compare les applets de commande Lync Server Management Shell utilisées pour préparer AD DS aux commandes LcsCmd utilisées pour préparer AD DS dans Microsoft Office Communications Server 2007 R2.

### <a name="cmdlets-compared-to-lcscmd"></a>Cmdlets par rapport à LcsCmd

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Applets</th>
<th>LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CSAdServerSchema</p></td>
<td><p>LcsCmd/Forest/action : SchemaPrep/SchemaType : Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>LcsCmd/Forest/action : CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>LcsCmd/Forest/action : ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>LcsCmd/Forest/action : ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>LcsCmd/Forest/action : CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>LcsCmd/Domain/action : DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>LcsCmd/Domain/action : DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>LcsCmd/Domain/action : CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Configuration requise pour Active Directory

Si l’héritage des autorisations est désactivé ou que les autorisations de l’utilisateur authentifié doivent être désactivées au sein de votre organisation, vous devez effectuer des étapes supplémentaires lors de la préparation du domaine. Pour plus d’informations, reportez-vous à [la rubrique préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

</div>

<div>

## <a name="custom-container-permissions"></a>Autorisations de conteneur personnalisé

Si votre organisation utilise des conteneurs personnalisés au lieu de trois conteneurs intégrés (utilisateurs, ordinateurs et contrôleurs de domaine), vous devez accorder l’accès en lecture aux conteneurs personnalisés pour le groupe utilisateurs authentifiés. L’accès en lecture aux conteneurs est requis pour la préparation du domaine. Pour plus d’informations, consultez [préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md).

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Utilisation des cmdlets et LDIFDE. exe

Dans l’étape **préparer le schéma** de l’Assistant Déploiement de Lync Server et de l’applet de commandes **installation-CsAdServerSchema** , étendez le schéma Active Directory sur les contrôleurs de domaine exécutant un système d’exploitation 64 bits. Si vous devez prolonger le schéma Active Directory sur un contrôleur de domaine exécutant un système d’exploitation 32 bits, vous pouvez exécuter l’applet de commande **install-CsAdServerSchema** à distance à partir d’un serveur membre (approche recommandée). Toutefois, si vous devez exécuter une préparation de schéma directement sur le contrôleur de domaine, vous pouvez utiliser l’outil LDIFDE. exe pour importer les fichiers de schéma. L’outil LDIFDE. exe est fourni avec la plupart des versions du système d’exploitation Windows.

Si vous utilisez LDIFDE. exe pour importer les fichiers de schéma, vous devez importer les quatre fichiers, que vous utilisiez la migration à partir d’une version précédente ou que vous effectuiez une nouvelle installation. Vous devez les importer dans l’ordre suivant :

1.  ExternalSchema. ldf

2.  ServerSchema. ldf

3.  BackCompatSchema. ldf

4.  VersionSchema. ldf

<div>


> [!NOTE]  
> Les quatre fichiers. ldf se trouvent dans l’annuaire \Support\Schema de votre support d’installation ou de votre téléchargement.



</div>

Pour utiliser Ldifde. exe pour importer les quatre fichiers de schéma sur un contrôleur de domaine qui est le maître de schéma, utilisez le format suivant :

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Par exemple :

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> Utilisez le paramètre b uniquement si vous êtes connecté en tant qu’un autre utilisateur. Pour plus d’informations sur les droits d’utilisateur requis, voir la section « privilèges d’administrateur et rôles » plus loin dans cette rubrique.



</div>

Pour utiliser Ldifde. exe pour importer les quatre fichiers de schéma sur un contrôleur de domaine qui n’est pas le maître de schéma, utilisez le format suivant :

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Pour plus d’informations sur l’utilisation de LDIFDE, voir l’article de la base de connaissances Microsoft 237677 « utilisation de LDIFDE pour importer et exporter [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)des objets d’annuaire dans Active Directory ».

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Préparation de la forêt pour Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

