---
title: 'Lync Server 2013 : restauration des données d’analyse ou d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9621fe3c1905dbd34fd3b4da39b2562c608d6355
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Restauration de données d’analyse ou d’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-18_

Il n’est pas nécessaire de restaurer les données de surveillance et d’archivage après un échec. Toutefois, si la surveillance et l’archivage de données sont essentielles pour votre organisation, vous pouvez restaurer les données une fois la nouvelle création de celles-ci.

La procédure suivante vous explique comment utiliser SQL Server Management Studio pour restaurer les données d’archivage et d’analyse des données.

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>Pour restaurer les données d’analyse ou d’archivage à partir d’un fichier de sauvegarde

1.  Ouvrez une session sur le serveur que vous restaurez en tant que membre du groupe Administrateurs sur l’ordinateur local ou un groupe disposant de droits d’utilisateur équivalents.

2.  Ouvrez SQL Server Management Studio : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft SQL Server 2012** ou **Microsoft SQL Server 2008 R2**, puis cliquez sur **SQL Server Management Studio**.

3.  Dans **connexion au serveur**, connectez-vous à l’instance SQL Server en fournissant au moins le nom du serveur et les informations d’authentification.

4.  Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur **bases de données**, puis cliquez sur **restaurer la base de données**.

5.  Sous **Sélectionner une page**, cliquez sur **général**, puis dans la **base de données** , sélectionnez le nom de la base de données comme suit :
    
      - Pour une base de données d’archivage, sélectionnez **LcsLog**.
    
      - Pour une base de données d’enregistrement des détails des appels, sélectionnez **LcsCDR**.
    
      - Pour une base de données de qualité de l’apprentissage (QoE), sélectionnez **QoEMetrics**.

6.  Cliquez sur **à partir de l’appareil**.

7.  Sous **sélectionnez les jeux de sauvegarde à restaurer**, cliquez sur le fichier de sauvegarde, puis cliquez sur **restaurer**.

8.  Sous **Sélectionner une page**, cliquez sur **options**, assurez-vous que le chemin d’accès et le chemin d’accès du fichier de données se trouvent dans le dossier approprié, puis cliquez sur **OK**.

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>Pour vous assurer que les listes de contrôle d’accès (ACL) sont correctes

1.  Développez **bases de données**, développez la base de données d’archivage ou de surveillance, développez **sécurité**, puis **utilisateurs**.

2.  Vérifiez que le groupe de domaine RTCComponentUniversalServices existe en tant qu’utilisateur.

3.  Si RTCComponentUniversalServices n’existe pas sous **utilisateurs**, procédez comme suit :
    
    1.  Cliquez avec le bouton droit sur **utilisateurs**, puis cliquez sur **nouvel utilisateur**.
    
    2.  Dans **nom de connexion**, tapez le nom de groupe manquant, RTCComponentUniversalServices.
    
    3.  Sous **appartenance aux rôles de base de données**, sélectionnez l’autorisation **ServerRole** , puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Vous n’avez pas besoin de redémarrer le service d’archivage ou de surveillance.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

