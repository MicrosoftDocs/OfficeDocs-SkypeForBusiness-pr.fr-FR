---
title: 'Lync Server 2013 : Création ou modification d’un numéro d’accès à une conférence rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8372c8117f2e33594ae59b3eff15c6d7eee96ba6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Création ou modification d’un numéro d’accès à une conférence rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-17_

Pour créer ou modifier un numéro d’accès à une conférence rendez-vous, procédez comme suit.

<div>


> [!IMPORTANT]  
> Avant de créer un numéro d’accès rendez-vous, vous devez définir une région de conférence rendez-vous pour le plan de numérotation associé au nouveau numéro d’accès par connexion. Plusieurs plans de numérotation peuvent utiliser la même région.



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>Pour créer ou modifier un numéro d’accès à une conférence rendez-vous

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.

4.  Dans la page **Numéro d’accès entrant**, effectuez l’une des opérations suivantes :
    
      - Cliquez sur **Nouveau** pour ouvrir **Nouveau numéro d’accès entrant**.
    
      - Cliquez sur l’un des numéros d’accès entrant dans la liste, cliquez sur **Modifier**, puis sur **Afficher les détails**.
        
        <div>
        

        > [!NOTE]  
        > Utiliser le champ de recherche pour rechercher le contenu d’une colonne dans la liste des numéros d’accès entrant peut ne pas produire les résultats que vous attendez. Par conséquent, triez la liste selon la colonne qui vous intéresse pour identifier le numéro d’accès entrant que vous voulez afficher ou modifier.

        
        </div>

5.  Dans **Numéro affiché**, tapez le numéro de téléphone que les utilisateurs du réseau téléphonique commuté (RTC) composent pour rejoindre une conférence.
    
    <div>
    

    > [!NOTE]  
    > Ce numéro est affiché dans les invitations aux réunions et dans la page web des paramètres des conférences rendez-vous.

    
    </div>

6.  In **Nom d’affichage**, tapez la description du numéro d’accès entrant. Il s’agit du nom associé au numéro d’accès rendez-vous dans les résultats de recherche Lync.
    
    <div>
    

    > [!NOTE]  
    > Ce nom est affiché dans le client lorsqu’un utilisateur appelle le numéro d’accès.

    
    </div>

7.  Dans **URI de ligne**, tapez le numéro E.164 du numéro d’accès entrant au format d’URI TEL, avec le symbole + avant le numéro et sans espace. Par exemple, tel :+14255550200.
    
    <div>
    

    > [!NOTE]  
    > Le même URI de ligne ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous.

    
    </div>

8.  Dans **URI SIP**, procédez comme suit :
    
      - Dans la zone de texte, tapez un URI SIP (Session Initiation Protocol) unique pour ce numéro d’accès à une conférence rendez-vous. Cet URI SIP est affiché à différents emplacements, y compris, mais sans s’y limiter, les messages de notification d’appel et les versions antérieures de clients Communicator.
        
        <div>
        

        > [!NOTE]  
        > Le même URI SIP ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous. Il n’est pas possible de modifier l’URI SIP une fois que le numéro d’accès est créé. Le seul moyen de modifier l’URI SIP est de supprimer et de recréer le numéro d’accès.

        
        </div>
    
      - Dans la zone de liste déroulante, cliquez sur le domaine de l’application de surveillance des conférences qui prend en charge ce numéro d’accès rendez-vous.

9.  Dans **Pool**, cliquez sur le pool qui exécute l’instance d’Intendant Conférence qui prend en charge ce numéro d’accès entrant.
    
    <div>
    

    > [!NOTE]  
    > Si vous devez modifier le pool après avoir créé le numéro d’accès, vous devez utiliser l’applet de commande <STRONG>Move-CsApplicationEndpoint</STRONG> ou supprimer et recréer le numéro d’accès.

    
    </div>

10. Dans **Langue principale**, cliquez sur la langue des invites pour ce numéro d’accès entrant.
    
    <div>
    

    > [!NOTE]  
    > La langue principale est la langue que l’Intendant Conférence utilise pour répondre aux appels. Les langues prises en charge sont affichées avec chaque numéro de téléphone d’accès dans la page web des paramètres des conférences rendez-vous.

    
    </div>

11. (Facultatif) Dans **Langues secondaires (quatre au maximum)**, cliquez sur **Ajouter**, sélectionnez les langues supplémentaires que vous souhaitez prendre en charge pour les personnes qui appellent ce numéro d’accès entrant, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez sélectionner jusqu’à quatre langues secondaires pour chaque numéro d’accès entrant. Les utilisateurs peuvent sélectionner une langue secondaire avant d’entrer l’ID de la conférence à laquelle ils souhaitent participer.

    
    </div>

12. Pour ajouter une région pour le numéro d’accès à la Conférence rendez-vous, sous **régions associées**, cliquez sur **Ajouter**, sélectionnez une ou plusieurs régions associées au plan de numérotation pour ce numéro d’accès rendez-vous, puis cliquez sur **OK**.

13. Pour supprimer une région du numéro d’accès entrant, sous **Régions associées**, cliquez sur la région que vous souhaitez supprimer, puis cliquez sur **Supprimer**.

14. Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

