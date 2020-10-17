---
title: 'Lync Server 2013 : restauration des données de surveillance ou d’archivage'
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
ms.openlocfilehash: 9e908792e8a2563094b11bcce73d4ac6ce6c7121
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511421"
---
# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Restauration des données de surveillance ou d’archivage dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-18_

La restauration des données de surveillance et d’archivage n’est pas nécessaire pour que Lync Server fonctionne après une défaillance. Toutefois, si les données de surveillance et d’archivage sont essentielles pour votre organisation, vous pouvez restaurer les données après avoir recréé les bases de données.

La procédure suivante explique comment utiliser SQL Server Management Studio pour restaurer des données d’archivage ou de surveillance.

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>Pour restaurer les données de surveillance ou d’archivage à partir d’un fichier de sauvegarde

1.  Ouvrez une session sur le serveur que vous restaurez en tant que membre du groupe Administrateurs sur l’ordinateur local ou un groupe avec des droits d’utilisateur équivalents.

2.  Ouvrez SQL Server Management Studio : cliquez **sur Démarrer**, **sur tous les programmes**, sur **Microsoft SQL Server 2012** ou **Microsoft SQL Server 2008 R2**, puis sur **SQL Server Management Studio**.

3.  Dans **Se connecter au serveur**, connectez-vous à l’instance SQL Server en fournissant au moins le nom du serveur et les informations d’authentification.

4.  Dans **Explorateur d’objets**, cliquez avec le bouton droit sur **Bases de données**, puis cliquez sur **Restaurer la base de données**.

5.  Sous **Sélectionner une page**, cliquez sur **Général**, puis dans **Vers la base de données** sélectionnez le nom de la base de données comme suit :
    
      - Pour une base de données d’archivage, sélectionnez **LcsLog**.
    
      - Pour une base de données CDR (enregistrement des détails des appels), sélectionnez **LcsCDR**.
    
      - Pour une base de données QoE (qualité de l’expérience), sélectionnez **QoEMetrics**.

6.  Cliquez sur **À partir de l’unité**.

7.  Sous **Sélectionnez les jeux de sauvegarde à restaurer**, cliquez sur le fichier de sauvegarde, puis cliquez sur **Restaurer**.

8.  Sous **Sélectionner une page**, cliquez sur **Options**, vérifiez que le chemin d’accès du fichier de données et que le chemin d’accès du journal sont dans le dossier voulu, puis cliquez sur **OK**.

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>Pour vous assurer que les listes de contrôle d’accès (ACL) sont correctes

1.  Développez **Bases de données**, développez la base de données d’archivage ou de surveillance, développez **Sécurité**, puis développez **Utilisateurs**.

2.  Vérifiez que le groupe de domaines RTCComponentUniversalServices existe en tant qu’utilisateur.

3.  Si RTCComponentUniversalServices n’existe pas sous **utilisateurs**, procédez comme suit :
    
    1.  Cliquez avec le bouton droit sur **Utilisateurs**, puis sur **Nouvel utilisateur**.
    
    2.  Dans **nom de connexion**, tapez le nom de groupe manquant, RTCComponentUniversalServices.
    
    3.  Sous **Appartenance au rôle de base de données**, sélectionnez l’autorisation **ServerRole**, puis cliquez sur **OK**.
    
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

