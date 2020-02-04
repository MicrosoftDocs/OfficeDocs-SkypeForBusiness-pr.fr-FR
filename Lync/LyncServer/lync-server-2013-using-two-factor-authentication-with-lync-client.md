---
title: 'Lync Server 2013 : utilisation de l’authentification à deux facteurs avec le client Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25b5d3305c5d9825342c0293325c9afca96c5a97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>Utilisation de l’authentification à deux facteurs avec le client Lync et Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-11_

Cette rubrique vous explique comment tirer parti de l’authentification à deux facteurs avec le client 2013 Lync.

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>Se connecter à Lync 2013 pour la première fois

Vos informations de connexion à Lync sont généralement configurées automatiquement lorsque Lync 2013 est installé. La première fois que vous utilisez Lync, il est possible que vous deviez démarrer manuellement le client.

**Pour vous connecter à Lync pour la première fois**

1.  Ouvrez une session sur le réseau de votre organisation.

2.  Sélectionnez **Démarrer** \> **tous les programmes** \> **Microsoft \> Lync Lync 2013**.
    
    L’écran de connexion Lync doit apparaître.
    
      - Si la zone Adresse de connexion est déjà renseignée, vérifiez que l’adresse affichée est correcte.
    
      - Si ce n’est pas le cas, ou si la zone est vide, entrez votre adresse de connexion Lync (il s’agit généralement de votre adresse de messagerie).
    
      - Si la zone Mot de passe qui s’affiche n’est pas renseignée, ajoutez votre mot de passe.

3.  Sélectionnez **Se connecter**.

</div>

<div>

## <a name="sign-out-of-lync"></a>Se déconnecter de Lync

Lorsque vous avez terminé d’utiliser Lync, vous pouvez fermer l’affichage, vous déconnecter de votre session ou quitter le programme à partir du menu fichier. Le tableau ci-dessous explique les différences entre ces trois options :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Action</th>
<th>Utilisation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Fermer</p></td>
<td><p>Ferme votre affichage Lync tout en permettant à la session Lync identifiée avec votre ID d’utilisateur de continuer à s’exécuter. Cela vous permet de continuer à recevoir des notifications et à interagir avec d’autres personnes.</p>
<p>Vous pouvez obtenir l’affichage à tout moment en cliquant sur l’icône Lync dans la barre des tâches ou dans la zone de notification située en bas de votre écran.</p></td>
<td><p>Dans la fenêtre principale de Lync, effectuez l’une des opérations suivantes :</p>
<ol>
<li><p>Sélectionnez le <strong>bouton Options</strong> , puis cliquez sur <strong>Fermer</strong>le <strong>fichier</strong> &gt; .</p></li>
<li><p>Cliquez sur le bouton <strong>Fermer</strong> (X) dans le coin supérieur droit de la fenêtre.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>Se déconnecter</p></td>
<td><p>Met fin à la session Lync associée à votre ID d’utilisateur, mais Lync continue de s’exécuter en arrière-plan. Lorsque vous vous déconnectez, la fenêtre de connexion s’affiche.</p>
<div>

> [!TIP]  
> Sélectionnez <STRONG>Supprimer mes informations de connexion</STRONG> lorsque vous vous déconnectez pour supprimer l’enregistrement de votre ID d’ouverture de session et le mot de passe de l’ordinateur. Cela permet au support technique de résoudre plus facilement les problèmes de connexion. Vos informations de connexion sont mieux sécurisées, car l’ouverture de session avec vos informations d’identification est plus difficile pour des utilisateurs non autorisés.


</div></td>
<td><p>Dans la fenêtre principale de Lync, cliquez sur le bouton <strong>options</strong> , <strong>puis sélectionnez</strong> &gt; <strong>se déconnecter</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Quitter</p></td>
<td><p>Met fin à votre session Lync et arrête Lync sur votre ordinateur. Après avoir quitté le programme, si vous souhaitez redémarrer Lync, cliquez sur <strong>Démarrer</strong> &gt; <strong>tous les programmes</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</p></td>
<td><p>Dans la fenêtre principale de Lync, cliquez sur le bouton <strong>options</strong> , puis sélectionnez <strong>fermeture</strong>de <strong>fichier</strong> &gt; .</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>Se connecter à Lync avec une carte à puce

Certaines organisations utilisent désormais une procédure de connexion à plusieurs étapes, appelée authentification à deux facteurs, pour renforcer la sécurité de leurs utilisateurs Lync 2013. Si vous utilisez cette option, vous avez besoin d’une carte à puce pour vous connecter à Lync. Les cartes à puce sont disponibles dans deux variétés, physiques et virtuelles :

  - **Physiques**   concernant la taille d’une carte de crédit. Vous l’insérez dans un lecteur de carte à puce lorsque vous vous connectez.

  - **Virtuel**   n’est pas un objet physique, mais un identificateur électronique qui est écrit sur un processeur spécial sur votre ordinateur, qui, par essence, génère la carte à puce sur votre ordinateur. Disponible uniquement sur les ordinateurs Windows 8 qui contiennent le processeur TPM (Trusted Platform Module).

<div>

## <a name="enroll-your-smart-card"></a>Inscription de votre carte à puce

Pour que vous puissiez vous connecter à l’aide d’une carte à puce, celle-ci doit être « inscrite »; autrement dit, vos informations d’identification d’utilisateur doivent être identifiées sur la carte. C’est le cas, qu’il s’agisse d’une carte physique ou virtuelle. Ce processus a pu être déjà exécuté par votre administrateur de serveur Lync. Si vous ne savez pas si vous avez terminé, contactez-les.

<div>


> [!NOTE]  
> Dans la mesure où chaque carte à puce virtuelle est associée uniquement à l’appareil sur lequel elle est installée, une carte séparée doit être inscrite pour chaque ordinateur Windows 8 que vous utilisez.



</div>

**Pour inscrire manuellement votre carte à puce**

1.  Ouvrez une session sur l’ordinateur sur lequel vous exécutez Lync.

2.  À l’aide d’Internet Explorer, accédez à la page d’inscription web de l’autorité de certification de votre organisation.
    
    Si ce n’est déjà fait, demandez à votre administrateur de serveur Lync l’adresse Web de cette ressource. L’URL ressemble à ceci : https://MyCA.\[nom\]. com/certsrv.
    
    <div>
    

    > [!NOTE]  
    > Si vous utilisez Internet Explorer 10, vous devrez peut être afficher ce site web en mode de compatibilité.

    
    </div>

3.  Lorsque vous êtes invité à ouvrir une session dans la page de certification, connectez-vous à l’aide de votre compte de domaine (plutôt qu’en tant qu’administrateur de votre ordinateur).

4.  Dans la page d’accueil du site web, sélectionnez **Demander un certificat**.

5.  Sélectionnez **Demande avancée**.

6.  Sélectionnez **Créer et envoyer une demande auprès de cette autorité de certification**, puis cliquez sur **Suivant**.

7.  La page Station d’inscription de carte à puce s’affiche. Acceptez la demande d’installation du contrôle ActiveX, puis renseignez les champs de l’écran Demande de certificat avancée, comme suit :
    
    1.  Sélectionnez **Utilisateur de carte à puce** dans la liste déroulante **Modèle de certificat**.
    
    2.  Sélectionnez **Créer un jeu de clés**.
    
    3.  Recherchez les informations relatives au fabricant sur l’étiquette de votre carte à puce, puis sélectionnez le fabricant dans la liste déroulante **Fournisseur de services de chiffrement**.
    
    4.  Sélectionnez **Fournisseur de services de chiffrement** comme format de la demande, si cette option n’est pas déjà sélectionnée.
    
    5.  Dans la liste déroulante Algorithme de hachage, sélectionnez **sha1** si cette option n’est pas déjà sélectionnée.
    
    6.  Attribuez un nom reconnaissable à votre certificat, puis cliquez sur **Envoyer**.

8.  Insérez votre carte à puce vierge dans le lecteur de cartes relié à la station d’inscription, puis cliquez sur **Inscrire**.

9.  Lorsque vous y êtes invité, entrez votre code confidentiel, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Si le support technique ne vous a pas communiqué de code confidentiel spécial pour inscrire votre carte à puce, utilisez la valeur de code confidentiel par défaut de la carte à puce (12345678).

    
    </div>

10. Sélectionnez l’option forçant l’utilisateur (vous) à modifier le code confidentiel à la première utilisation de la carte.

11. Insérez votre carte à puce vierge dans le lecteur de cartes relié à la station d’inscription, puis cliquez sur **Inscrire**.

12. Lorsque vous y êtes invité, entrez votre code confidentiel, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Si le support technique ne vous a pas communiqué de code confidentiel spécial pour inscrire votre carte à puce, utilisez la valeur de code confidentiel par défaut de la carte à puce (12345678).

    
    </div>

13. Sélectionnez l’option forçant l’utilisateur (vous) à modifier le code confidentiel à la première utilisation de la carte.

14. Cliquez sur **OK** pour confirmer que le certificat affiché inclut vos informations.

15. Une fois que vous recevez l’avis confirmant l’émission du certificat, cliquez sur **Installer ce certificat** pour terminer la procédure d’inscription.

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>Connectez-vous à Lync à l’aide de vos informations d’identification de carte à puce

Avant d’utiliser votre carte à puce pour la première fois, il est recommandé de cliquer sur **Supprimer mes informations de connexion** dans la page de connexion à Lync. Cela permet de supprimer les informations d’identification de connexion stockées sur votre ordinateur et d’éliminer une source possible d’erreur.

**Pour vous connecter à Lync à l’aide de vos informations d’identification de carte à puce**

1.  Démarrez le client Lync.

2.  Dans l’écran Se connecter, tapez le nom de compte d’utilisateur de connexion dans la zone **Adresse de connexion**, puis cliquez sur **Se connecter**.

3.  Si vous utilisez une carte à puce virtuelle, ignorez cette étape.
    
    Si vous utilisez une carte à puce physique, insérez la carte à puce dans le lecteur de cartes à puce, puis, lorsque vous y êtes invité, cliquez sur **OK** lorsque la carte est détectée.

4.  Tapez le code confidentiel de votre carte à puce, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Si le support technique ne vous a pas communiqué de code confidentiel, utilisez la valeur par défaut (12345678).

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

