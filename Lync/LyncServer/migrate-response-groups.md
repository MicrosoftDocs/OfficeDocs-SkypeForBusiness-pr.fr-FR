---
title: Migrer des groupes Response Group
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
ms.openlocfilehash: 23ef26b86b1de3fa7f9656cdb2ea82bb7a220948
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrer des groupes Response Group

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-09-23_

Après avoir déplacé vos utilisateurs vers les pools Lync Server 2013, vous pouvez migrer vos groupes de réponse. La migration de groupes de réponse inclut la copie de groupes d’agents, de files d’attente, de flux de travail, de fichiers audio et de déplacements de groupe de réponses de l’ancien déploiement au pool Lync Server 2013. Après la migration de vos groupes de réponse hérités, les appels vers les groupes de réponse sont gérés par l’application Response Group dans le pool Lync Server 2013. Les appels de Response Groups ne sont plus gérés par le pool hérité.

<div>


> [!NOTE]  
> Même si vous pouvez migrer des groupes de réponses avant de déplacer tous les utilisateurs vers le pool Lync Server 2013, nous vous recommandons de déplacer d’abord tous les utilisateurs. En particulier, les utilisateurs qui sont agents de groupe de réponse ne disposeront pas de toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils ne seront pas déplacés vers le pool Lync Server 2013.



</div>

Avant de migrer des groupes de réponse, vous devez avoir déployé un pool Lync Server 2013 qui inclut l’application Response Group. L’application Response Group est installée et activée par défaut lorsque vous déployez Enterprise Voice. Vous pouvez vous assurer que l’application Response Group est installée en exécutant l’applet de demande **Get-CsService-ApplicationServer** .

<div>


> [!NOTE]  
> Vous pouvez créer des groupes de réponse Lync Server 2013 dans le pool Lync Server 2013 avant de migrer vos groupes de réponse hérités.



</div>

Pour migrer des groupes de réponse d’un pool hérité vers Lync Server 2013, exécutez l’applet de **passe Move-CsRgsConfiguration** .

<div>


> [!IMPORTANT]  
> L’applet de passe de migration de groupe de réponse déplace la configuration de groupe de réponse pour le pool entier. Vous ne pouvez pas sélectionner des groupes, des files d’attente ou des flux de travail spécifiques à migrer.



</div>

Une fois les groupes de réponse migrés, vous devez utiliser le panneau de configuration de Lync Server ou les applets de commande Lync Server Management Shell pour vérifier le déplacement de tous les groupes d’agents, files d’attente et flux de travail.

Lorsque vous migrez des groupes de réponse, les groupes de réponse Lync Server 2010 ne sont pas supprimés. Lorsque vous gérez des groupes de réponses après la migration à l’aide du panneau de configuration de Lync Server ou de Lync Server Management Shell, vous pouvez voir les groupes de réponse Lync Server 2010 et les groupes de réponse Lync Server 2013. Vous devez appliquer les mises à jour uniquement aux groupes de réponse Lync Server 2013. Les groupes de réponse Lync Server 2010 sont conservés uniquement à des fins de restauration.

<div>


> [!WARNING]  
> Une fois la migration effectuée et les nouveaux groupes de réponse créés, le panneau de configuration de Lync Server et Lync Server Management Shell affichent les versions Lync Server 2010 et Lync Server 2013 de chaque groupe de réponses. N’utilisez pas le panneau de configuration de Lync Server ou Lync Server Management Shell pour supprimer les groupes de réponse Lync Server 2010. Si vous supprimez un, le groupe de réponse correspondant qui a été créé lors de la migration ne fonctionnera plus. Les groupes de réponse Lync Server 2010 seront supprimés lorsque vous désaffectez le pool Lync Server 2010.



</div>

<div>


> [!IMPORTANT]  
> Nous vous recommandons de ne pas supprimer les données de votre déploiement antérieur tant que vous n’avez pas désactivé le pool. Par ailleurs, nous vous conseillons vivement d’exporter des groupes de réponse immédiatement après la migration. Si un groupe de réponse Lync Server 2010 doit être supprimé, vous pouvez restaurer vos groupes de réponse à partir de la sauvegarde pour obtenir les groupes de réponse Lync Server 2013 en cours d’exécution.



</div>

Lync Server 2013 introduit une nouvelle fonctionnalité de groupe de réponse appelée **type de flux de travail**. Le **type de flux de travail** peut être **géré** ou **non**géré. Tous les groupes de réponses sont migrés avec le **type de flux de travail** défini sur **non géré** et avec une liste de gestionnaires vide.

Lorsque vous exécutez l’applet de cmdlet **Move-CsRgsConfiguration** , les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration. Toutefois, si vous avez besoin de revenir au pool hérité, vous devez exécuter l’applet de passe **Move-CsApplicationEndpoint** pour replacer les objets de contact sur le pool hérité.

La procédure suivante pour la migration de configurations de groupe de réponse suppose que vous disposez d’une relation un-à-un entre vos pools hérités et les pools Lync Server 2013. Si vous envisagez de consolider ou de fractionner des listes lors de la migration et du déploiement, vous devez planifier les mappages de pool hérité par le pool Lync Server 2013.

<div>

## <a name="to-migrate-response-group-configurations"></a>Pour migrer les configurations de Response Group

1.  Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalServerAdmins ou disposant d’autorisations et de droits d’administrateur équivalents.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Par exemple :
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Après avoir migré des groupes de réponses et des agents vers le pool Lync Server 2013, l’URL utilisée par les agents pour se connecter et se déconnecter est une URL Lync Server 2013 et est disponible dans le menu **Outils** . Rappelez aux agents de mettre à jour les références, comme les signets, à la nouvelle URL.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Pour vérifier la migration du groupe de réponse à l’aide du panneau de configuration de Lync Server

1.  Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui est membre du rôle CsViewOnlyAdministrator.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans le volet de navigation de gauche, cliquez sur **Response Groups**.

4.  Dans l’onglet **flux de travail** , vérifiez que tous les flux de travail de votre environnement Lync Server 2010 sont inclus dans la liste.

5.  Cliquez sur l’onglet **file d’attente** pour vérifier que toutes les files d’attente de votre environnement Lync Server 2010 sont incluses dans la liste.

6.  Cliquez sur l’onglet **groupe** , puis vérifiez que tous les groupes d’agents de votre environnement Lync Server 2010 sont inclus dans la liste.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>Pour vérifier la migration de groupe de réponse à l’aide de Lync Server Management Shell

1.  Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui est membre du rôle CsViewOnlyAdministrator.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.
    
    Pour plus d’informations sur les applets de commande suivantes, exécutez :
    
        Get-Help <cmdlet name> -Detailed

3.  Exécutez :
    
        Get-CsRgsAgentGroup

4.  Vérifiez que tous les groupes d’agents de votre environnement Lync Server 2010 sont inclus dans la liste.

5.  Exécutez :
    
        Get-CsRgsQueue

6.  Vérifiez que toutes les files d’attente de votre environnement Lync Server 2010 figurent dans la liste.

7.  Exécutez :
    
        Get-CsRgsWorkflow

8.  Vérifiez que tous les flux de travail de votre environnement Lync Server 2010 sont inclus dans la liste.

</div>

</div>

<span> </span>

</div>

</div>

</div>

