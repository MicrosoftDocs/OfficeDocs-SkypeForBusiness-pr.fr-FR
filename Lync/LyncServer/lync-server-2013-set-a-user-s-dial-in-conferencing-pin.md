---
title: 'Lync Server 2013: définir le code confidentiel de conférence rendez-vous d’un utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 258c6e5da1dc5b78d53bbc3779d50890935d7b58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>Définir le code confidentiel de conférence rendez-vous d’un utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-06-10_

Pour participer à une conférence rendez-vous en tant qu’utilisateur authentifié, un utilisateur de Lync Server 2013 avec les informations d’identification d’AD DS (Active Directory Domain Services) nécessite un code confidentiel (PIN). Si un utilisateur oublie le code confidentiel de conférence rendez-vous ou n’a pas défini le code confidentiel à l’aide de Lync Server, vous pouvez définir le code confidentiel de l’utilisateur à partir du panneau de configuration de Lync Server. Vous pouvez générer automatiquement le code confidentiel ou en créer un manuellement.

<div>


> [!NOTE]  
> Les caractéristiques spécifiques du code confidentiel, comme sa longueur minimale, peuvent être définies sous forme de stratégie. Outre la stratégie globale, vous pouvez configurer une stratégie de code confidentiel pour un site ou un utilisateur spécifique. Pour plus d’informations sur la configuration d’une stratégie de code confidentiel, reportez-vous à la rubrique <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">configurer les règles du code confidentiel pour les conférences rendez-vous dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-set-a-users-pin"></a>Pour définir le code confidentiel d’un utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
      - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).

5.  (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Différent de**).
    
    4.  Selon la propriété utilisateur sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche de la liste déroulante.
        
        <div>
        

        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.

        
        </div>
    
    5.  Cliquez sur **Rechercher**.
    
    <div>
    

    > [!NOTE]  
    > Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, sélectionnez l’utilisateur, cliquez sur <STRONG>Action</STRONG>, puis sur <STRONG>Déverrouiller le code confidentiel</STRONG>.

    
    </div>

6.  Sélectionnez un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Définir le code confidentiel**.

7.  Dans la boîte de dialogue **Définir le code confidentiel**, effectuez l’une des opérations suivantes :
    
      - Pour permettre à Lync Server 2013 de générer le code confidentiel de l’utilisateur, sélectionnez **générer automatiquement un code confidentiel valide** (par défaut).
    
      - Pour créer votre propre code confidentiel, cliquez sur **Entrer manuellement un code confidentiel spécifique**, cliquez sur la zone de texte, puis tapez un code confidentiel respectant les exigences de code confidentiel spécifiées dans vos paramètres de stratégie de code confidentiel.

8.  Cliquez sur **OK**.

9.  Dans **Définir le code confidentiel**, effectuez l’une des opérations suivantes :
    
      - Activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le et communiquez-le à l’utilisateur selon la méthode préférée de votre organisation.
    
      - Cliquez sur **Ouvrir mon application de messagerie pour envoyer le nouveau code confidentiel à l’utilisateur** afin d’envoyer le code confidentiel par courrier électronique. Si Microsoft Office Outlook est votre client de messagerie, le code confidentiel est copié automatiquement dans un nouveau message électronique. Si vous utilisez un autre client de messagerie, activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le dans votre message électronique.

10. Cliquez sur **Fermer**.

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Attribution d’un code confidentiel utilisateur à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez également affecter plusieurs codes confidentiels à l’aide de l’applet de commande Set-CsClientPin. Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>Affectation automatique d’un code confidentiel à un utilisateur

  - La commande ci-dessous affecte un code confidentiel à l’utilisateur Ken Myer. Dans la mesure où le paramètre code confidentiel n’est pas inclus, Lync Server génère automatiquement et attribue le numéro de broche.
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>Affectation d’un code confidentiel à un utilisateur

  - Cette commande utilise le paramètre de code confidentiel pour affecter le code confidentiel 121989 à l’utilisateur Ken Myer.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Numéro d’accès entrant](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))  


[Configurer des règles de code confidentiel (PIN) de conférence rendez-vous dans Lync Server 2013](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

