---
title: 'Lync Server 2013 : définition du code confidentiel de conférence rendez-vous d’un utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad28eb7214cb6762e8b0941f22da8b97966e9024
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>Définir le code confidentiel de conférence rendez-vous d’un utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-10_

Pour joindre une conférence rendez-vous en tant qu’utilisateur authentifié, un utilisateur Lync Server 2013 avec les informations d’identification des services de domaine Active Directory (AD DS) nécessite un code confidentiel (PIN). Si un utilisateur oublie le code confidentiel de la Conférence rendez-vous ou n’a pas défini le code confidentiel à l’aide de Lync Server, vous pouvez définir le code confidentiel de l’utilisateur à partir du panneau de configuration Lync Server. Vous pouvez générer automatiquement le code confidentiel ou en créer un manuellement.

<div>


> [!NOTE]  
> Les caractéristiques spécifiques du code confidentiel, comme sa longueur minimale, peuvent être définies en tant que stratégie. En plus de la stratégie globale, vous pouvez configurer une stratégie de code confidentiel pour un site ou un utilisateur particulier. Pour plus d’informations sur la configuration d’une stratégie de code confidentiel, voir <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">configurer des règles de code confidentiel (pin) pour les conférences rendez-vous dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-set-a-users-pin"></a>Pour définir le code confidentiel d’un utilisateur

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
      - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).

5.  (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).
    
    4.  Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.
        
        <div>
        

        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.

        
        </div>
    
    5.  Cliquez sur **Rechercher**.
    
    <div>
    

    > [!NOTE]  
    > Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, cliquez sur l’utilisateur, sur <STRONG>Action</STRONG>, puis sur <STRONG>Déverrouiller le code confidentiel</STRONG>.

    
    </div>

6.  Cliquez sur un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Définir le code confidentiel**.

7.  Dans la boîte de dialogue **Définir le code confidentiel**, effectuez l’une des opérations suivantes :
    
      - Pour permettre à Lync Server 2013 de générer le code confidentiel de l’utilisateur, sélectionnez **générer automatiquement un code confidentiel valide** (valeur par défaut).
    
      - Pour créer votre propre code confidentiel, cliquez sur **Entrer manuellement un code confidentiel spécifique**, cliquez sur la zone de texte, puis tapez un code confidentiel respectant les exigences de code confidentiel spécifiées dans vos paramètres de stratégie de code confidentiel.

8.  Cliquez sur **OK**.

9.  Dans **Définir le code confidentiel**, effectuez l’une des opérations suivantes :
    
      - Activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le et communiquez-le à l’utilisateur selon la méthode préférée de votre organisation.
    
      - Cliquez sur **Ouvrir mon application de messagerie pour envoyer le nouveau code confidentiel à l’utilisateur** afin d’envoyer le code confidentiel par courrier électronique. Si Microsoft Office Outlook est votre client de messagerie, le code confidentiel est automatiquement copié dans un nouveau message électronique. Si vous utilisez un autre client de messagerie, activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le dans votre message électronique.

10. Cliquez sur **Fermer**.

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Affectation d’un code confidentiel d’utilisateur à l’aide d’applets de commande Windows PowerShell

Vous pouvez attribuer des numéros de code confidentiel à l’aide de la cmdlet Set-CsClientPin. Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>Affectation automatique d’un code confidentiel à un utilisateur

  - La commande suivante affecte un code confidentiel à l’utilisateur Ken Myer. Étant donné que le paramètre de code confidentiel n’est pas inclus, Lync Server génère et affecte automatiquement le numéro de code confidentiel.
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>Pour affecter un numéro de code confidentiel spécifique à un utilisateur

  - Cette commande utilise le paramètre de code confidentiel pour affecter le code confidentiel 121989 à l’utilisateur Ken Myer.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Numéro d’accès entrant](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))  


[Configurer des règles de code confidentiel (PIN) de conférence rendez-vous dans Lync Server 2013](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

