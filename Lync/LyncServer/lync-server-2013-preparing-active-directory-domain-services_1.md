---
title: 'Lync Server 2013 : Préparation des services de domaine Active Directory'
TOCTitle: Préparation des services de domaine Active Directory
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398607(v=OCS.15)
ms:contentKeyID: 49297820
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Préparation des services de domaine Active Directory dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Dans Lync Server 2013, vous pouvez utiliser l’Assistant Déploiement de Lync Server pour préparer les services de domaine Active Directory, ou vous pouvez utiliser les applets de commande Lync Server Management Shell directement. Vous pouvez également utiliser l’outil de ligne de commande ldifde.exe directement sur vos contrôleurs de domaine, comme décrit plus bas dans cet article.

L’Assistant Déploiement de Lync Server vous guide tout au long des tâches de préparation d’Active Directory. L’Assistant Déploiement exécute les applets de commande Lync Server Management Shell. Cet outil est utile pour les environnements avec une topologie à un seul domaine et à une seule forêt ou avec une autre topologie semblable.

> [!IMPORTANT]  
> Vous pouvez déployer Lync Server dans une forêt ou un domaine où les contrôleurs de domaine exécutent des versions 32 bits de certains systèmes d’exploitation (pour plus d’informations, reportez-vous à <a href="lync-server-2013-active-directory-infrastructure-requirements.md">Configuration requise pour l’infrastructure Active Directory pour Lync Server 2013</a>). Cependant, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour exécuter la préparation du schéma, de la forêt et du domaine dans ces environnements, car l’Assistant Déploiement et les fichiers de prise en charge sont en 64 bits uniquement. À la place, vous pouvez utiliser ldifde.exe et les fichiers .ldf associés sur un contrôleur de domaine 32 bits pour préparer le schéma, la forêt et le domaine. Reportez-vous à la section « Utilisation des applets de commande et de Ldifde.exe » dans cette rubrique.

Vous pouvez utiliser les applets de commande Lync Server Management Shell pour exécuter des tâches à distance ou pour des environnements plus complexes.

## Conditions préalables à la préparation d’Active Directory

Vous devez exécuter les étapes de préparation Active Directory sur un ordinateur exécutant Windows Server 2012, Windows Server 2012 R2 ou Windows Server 2008 R2 avec SP1 (64 bits). La préparation Active Directory nécessite Lync Server Management Shell et OCSCore.

Les composants suivants sont requis pour exécuter les tâches de préparation d’Active Directory :

  - Composants principaux de Lync Server (OCScore.msi)
    
    > [!NOTE]  
    > Si vous prévoyez d’utiliser Lync Server Management Shell pour la préparation d’Active Directory, vous devez exécuter l’Assistant Déploiement de Lync Server pour installer d’abord les composants principaux.

  - Microsoft .NET Framework 4.5
    
    > [!NOTE]  
    > Pour Windows Server 2012 et Windows Server 2012 R2, vous installez et activez .NET Framework 4.5 avec le Gestionnaire de serveur. Pour plus d’informations, reportez-vous à « Microsoft .NET Framework 4.5 » dans <a href="lync-server-2013-additional-software-requirements.md">Autre configuration logicielle requise pour Lync Server 2013</a>. Pour Windows Server 2008 R2, téléchargez et installez <a href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.Net Framework 4.5</a> à partir du site web Microsoft.

  - Outils d’administration de serveur distant (RSAT)
    
    > [!NOTE]  
    > Certains outils RSAT sont nécessaires si vous exécutez les étapes de préparation d’Active Directory sur un serveur membre plutôt que sur un contrôleur de domaine. Installez les composants logiciel enfichables AD DS et les outils de ligne de commande, ainsi que le module Active Directory pour Windows PowerShell à partir des services AD DS et du nœud Outils AD LDS du Gestionnaire de serveur.

  - Microsoft Visual C++ 2011 Redistributable
    
    > [!NOTE]  
    > Le programme d’installation vous invite à l’installer s’il n’est pas déjà sur l’ordinateur. Le package vous est fourni, il est inutile de l’acquérir séparément.

  - Windows PowerShell 3.0 (64 bits)
    
    Pour Windows Server 2012 et Windows Server 2012 R2, Windows PowerShell 3.0 doit être inclus avec votre installation de Lync Server 2013. Pour Windows Server 2008 R2, vous devez installer ou effectuer une mise à niveau vers Windows PowerShell 3.0. Pour plus d’informations, reportez-vous à [Installation de Windows PowerShell 3.0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

## Droits et rôles d’administrateur

Le tableau ci-après répertorie les droits et rôles d’administration requis pour chaque tâche de préparation d’Active Directory.

### Droits de l’utilisateur requis pour la préparation d’Active Directory

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Procédure</th>
<th>Droits ou rôles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Préparation du schéma</p></td>
<td><p>Membre du groupe Administrateurs du schéma pour le domaine racine de la forêt et droits d’administrateur sur le contrôleur de schéma</p></td>
</tr>
<tr class="even">
<td><p>Préparation de la forêt</p></td>
<td><p>Membre du groupe Administrateurs de l’entreprise pour la forêt</p></td>
</tr>
<tr class="odd">
<td><p>Préparation du domaine</p></td>
<td><p>Membre du groupe Administrateurs de l’entreprise ou Administrateurs du domaine pour le domaine spécifié</p></td>
</tr>
</tbody>
</table>


## Applets de commande de préparation d’Active Directory

Le tableau ci-dessous compare les applets de commande Lync Server Management Shell utilisées pour préparer AD DS aux commandes LcsCmd utilisées pour préparer AD DS dans Microsoft Office Communications Server 2007 R2.

### Comparaison des applets de commande et de LcsCmd

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Applets de commande</th>
<th>LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CSAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:SchemaPrep /SchemaType:Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CSAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CSAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CSAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CSAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CSAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CSAdDomain</p></td>
<td><p>Lcscmd /domain /action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CSAdDomain</p></td>
<td><p>Lcscmd /domain /action:CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


## Configuration requise pour des services de domaine Active Directory verrouillés

Si l’héritage des autorisations est désactivé ou que les autorisations des utilisateurs authentifiés doivent être désactivées dans votre organisation, vous devez exécuter des étapes supplémentaires dans le cadre de la procédure de préparation d’un domaine. Pour plus d’informations, reportez-vous à [Préparation des services de domaine Active Directory verrouillés dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

## Autorisations de conteneur personnalisé

Si votre organisation utilise des conteneurs personnalisés à la place des trois conteneurs intégrés (Utilisateurs, Ordinateurs et Contrôleurs de domaine), vous devez octroyer au groupe Utilisateurs authentifiés un accès en lecture aux conteneurs personnalisés. L’accès en lecture aux conteneurs est obligatoire pour la préparation du domaine. Pour plus d’informations, reportez-vous à [Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md).

## Utilisation des applets de commande et de Ldifde.exe

L’étape **Préparer un schéma** de l’Assistant Déploiement de Lync Server er l’applet de commande **Install-CsAdServerSchema** permettent d’étendre le schéma Active Directory sur des contrôleurs de domaine qui exécutent un système d’exploitation 64 bits. Si vous devez étendre le schéma Active Directory sur un contrôleur de domaine qui exécute un système d’exploitation 32 bits, vous pouvez exécuter l’applet de commande **Install-CsAdServerSchema** à distance depuis un serveur membre (approche recommandée). Si toutefois vous devez exécuter la préparation du schéma directement sur le contrôleur de domaine, vous pouvez utiliser l’outil Ldifde.exe pour importer les fichiers de schéma. L’outil Ldifde.exe est livré avec la plupart des versions du système d’exploitation Windows.

Si vous utilisez Ldife.exe pour importer les fichiers de schéma, vous devez importer les quatre fichiers, même si vous procédez à une migration depuis une version précédente ou à une nouvelle installation. Vous devez les importer dans l’ordre suivant :

1.  ExternalSchema.ldf

2.  ServerSchema.ldf

3.  BackCompatSchema.ldf

4.  VersionSchema.ldf

> [!NOTE]  
> Les quatre fichiers .ldf se trouvent dans le répertoire \Support\Schema de votre support d’installation ou de téléchargement.

Pour utiliser Ldifde.exe pour importer les quatre fichiers de schéma sur un contrôleur de domaine qui est également le contrôleur de schéma, utilisez le format suivant :

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Exemple :

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

> [!NOTE]  
> Utilisez le paramètre b seulement si vous êtes connecté en tant qu’un autre utilisateur. Pour plus d’informations sur les droits d’utilisateur requis, reportez-vous à la section « Droits et rôles d’administrateur » abordée précédemment dans cette rubrique.

Pour utiliser Ldifde.exe pour importer les quatre fichiers de schéma sur un contrôleur de domaine qui n’est pas le contrôleur de schéma, utilisez le format suivant :

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Pour plus d’informations sur l’utilisation de Ldifde, consultez l’article 237677 de la Base de connaissances Microsoft, « Utilisation de LDIFDE pour importer et exporter des objets d’annuaire vers Active Directory », à l’adresse [http://go.microsoft.com/fwlink/?linkid=132204\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=132204%26clcid=0x40c).

## Dans cette section

  - [Préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Préparation de la forêt pour Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md)

