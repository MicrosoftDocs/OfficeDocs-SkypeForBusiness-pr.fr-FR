---
title: Effectuer la migration de groupes Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d69bcdffdb420d0c79d049f83ab5fa23ddc968
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Effectuer la migration de groupes Response Group

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-09-23_

Une fois les utilisateurs déplacés vers les pools Lync Server 2013, vous pouvez migrer vos groupes Response Group. La migration de groupes Response Group consiste à copier des groupes d’agents, des files d’attente, des flux de travail, des fichiers audio et des objets de contact de groupe Response Group à partir du déploiement hérité vers le pool Lync Server 2013. Une fois vos groupes de réponse hérités migrés, les appels vers les groupes Response Group sont gérés par l’application Response Group dans le pool Lync Server 2013. Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.

<div>


> [!NOTE]  
> Bien que vous puissiez migrer des groupes Response Group avant de déplacer tous les utilisateurs vers le pool Lync Server 2013, nous vous recommandons de déplacer tous les utilisateurs en premier. En particulier, les utilisateurs qui sont des agents Response Group ne disposent pas de toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils ne sont pas déplacés vers le pool Lync Server 2013.



</div>

Avant de migrer les groupes Response Group, vous devez avoir déployé un pool Lync Server 2013 qui inclut l’application Response Group. L’application Response Group est installée et activée par défaut lorsque vous déployez voix entreprise. Vous pouvez vous assurer que l’application Response Group est installée en exécutant la cmdlet **Get-CsService-ApplicationServer** .

<div>


> [!NOTE]  
> Vous pouvez créer des groupes de réponses Lync Server 2013 dans le pool Lync Server 2013 avant de migrer vos groupes de réponses hérités.



</div>

Pour migrer des groupes Response Group d’un pool hérité vers le Lync Server 2013, exécutez la cmdlet **Move-applet csrgsconfiguration** .

<div>


> [!IMPORTANT]  
> La cmdlet Response Group migration déplace la configuration Response Group pour l’ensemble du pool. Vous ne pouvez pas sélectionner de groupes, files d’attente ou flux de travail spécifiques à migrer.



</div>

Après avoir migré les groupes Response Group, vous devez utiliser le panneau de configuration Lync Server ou les applets de commande Lync Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail ont été déplacés avec succès.

Lorsque vous migrez des groupes Response Group, les groupes Response Group de Lync Server 2010 ne sont pas supprimés. Lorsque vous gérez des groupes Response Group après une migration à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell, vous pouvez voir les groupes de réponse Lync Server 2010 et les groupes Response Group Lync Server 2013. Vous devez appliquer les mises à jour uniquement aux groupes Response Group Lync Server 2013. Les groupes Response Group de Lync Server 2010 sont conservés uniquement à des fins de restauration.

<div>


> [!WARNING]  
> Une fois la migration terminée et les nouveaux groupes Response Group créés, le panneau de configuration Lync Server et Lync Server Management Shell affichent les versions Lync Server 2010 et Lync Server 2013 de chaque groupe Response Group. N’utilisez pas le panneau de configuration Lync Server ni Lync Server Management Shell pour supprimer les groupes Response Group Lync Server 2010. Si vous supprimez un, le groupe Response Group correspondant qui a été créé pendant la migration cessera de fonctionner. Les groupes de réponses Lync Server 2010 sont supprimés lorsque vous désactivez le pool Lync Server 2010.



</div>

<div>


> [!IMPORTANT]  
> Nous vous recommandons de ne pas supprimer les données de votre déploiement précédent tant que vous n’avez pas désaffecté le pool. En outre, nous vous recommandons fortement d’exporter les groupes Response Group immédiatement après la migration. Si un groupe de réponse Lync Server 2010 doit être supprimé, vous pouvez restaurer vos groupes Response Group à partir de la sauvegarde pour obtenir les groupes de réponses Lync Server 2013 en cours d’exécution à nouveau.



</div>

Lync Server 2013 introduit une nouvelle fonctionnalité Response Group appelée **type de flux de travail**. Le **Type de flux de travail** peut être **Géré** ou **Non géré**. Tous les groupes Response Group sont migrés avec le **Type de flux de travail** défini à **Non géré** et avec une liste de gestionnaires vide.

Lorsque vous exécutez l’applet de commande **Move-applet csrgsconfiguration** , les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration. Toutefois, si vous devez restaurer le pool hérité, vous devez exécuter la cmdlet **Move-CsApplicationEndpoint** pour déplacer les objets contact vers le pool hérité.

La procédure suivante pour migrer des configurations de groupe Response Group suppose que vous avez une relation un-à-un entre vos pools hérités et les pools Lync Server 2013. Si vous envisagez de consolider ou de fractionner les pools au cours de votre migration et de votre déploiement, vous devez planifier le pool hérité mappé vers le pool Lync Server 2013.

<div>

## <a name="to-migrate-response-group-configurations"></a>Pour migrer des configurations de groupe Response Group

1.  Ouvrez une session sur l’ordinateur en utilisant un compte membre du groupe RTCUniversalServerAdmins ou disposant de droits et d’autorisations d’administrateur équivalents.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Générer
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Par exemple :
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Une fois que vous avez migré les groupes Response Group et les agents vers le pool Lync Server 2013, l’URL que les agents utilisent pour se connecter et se déconnecter est une URL Lync Server 2013 et est disponible dans le menu **Outils** . Rappelez aux agents de mettre à jour les références, telles que les signets, vers la nouvelle URL.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Pour vérifier la migration de Response Group à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans le volet de navigation gauche, cliquez sur **Services Response Group**.

4.  Sous l’onglet **flux de travail** , vérifiez que tous les flux de travail de votre environnement Lync Server 2010 sont inclus dans la liste.

5.  Cliquez sur l’onglet **file d’attente** , puis vérifiez que toutes les files d’attente de votre environnement Lync Server 2010 sont incluses dans la liste.

6.  Cliquez sur l’onglet **groupe** , puis vérifiez que tous les groupes d’agents de votre environnement Lync Server 2010 sont inclus dans la liste.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>Pour vérifier la migration de groupes Response Group à l’aide de Lync Server Management Shell

1.  Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.
    
    Pour plus d’informations sur les applets de commande suivantes, exécutez :
    
        Get-Help <cmdlet name> -Detailed

3.  Générer
    
        Get-CsRgsAgentGroup

4.  Vérifiez que tous les groupes d’agents de votre environnement Lync Server 2010 sont inclus dans la liste.

5.  Générer
    
        Get-CsRgsQueue

6.  Vérifiez que toutes les files d’attente de votre environnement Lync Server 2010 sont incluses dans la liste.

7.  Générer
    
        Get-CsRgsWorkflow

8.  Vérifiez que tous les flux de travail de votre environnement Lync Server 2010 sont inclus dans la liste.

</div>

</div>

<span> </span>

</div>

</div>

</div>

