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
ms.openlocfilehash: a90dd3c40267f0994e7f41eabb689c869182cea7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508641"
---
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>Utilisation de l’authentification à deux facteurs avec le client Lync et Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-11_

Cette rubrique décrit comment tirer parti de l’authentification à deux facteurs avec le client Lync 2013.

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>Connexion à Lync 2013 pour la première fois

Vos informations de connexion Lync sont généralement configurées automatiquement lors de l’installation de Lync 2013. Toutefois, la première fois que vous utilisez Lync, vous devrez peut-être démarrer manuellement le client.

**Pour vous connecter à Lync pour la première fois**

1.  Ouvrez une session sur le réseau de votre organisation.

2.  Sélectionnez **Démarrer** \> **tous les programmes** \> **Microsoft Lync \> Lync 2013**.
    
    L’écran de connexion Lync doit s’afficher.
    
      - Si la zone adresse de connexion est déjà renseignée, vérifiez que l’adresse indiquée est correcte.
    
      - Si ce n’est pas le cas, ou si la zone est vide, entrez votre adresse de connexion Lync (il s’agit généralement de la même chose que votre adresse de messagerie).
    
      - Si une zone de mot de passe vide est affichée, ajoutez votre mot de passe.

3.  Sélectionnez **connexion**.

</div>

<div>

## <a name="sign-out-of-lync"></a>Se déconnecter de Lync

Lorsque vous avez terminé d’utiliser Lync, vous pouvez fermer l’affichage, vous déconnecter de votre session ou quitter le programme, tout cela à partir du menu fichier. Le tableau suivant décrit les différences entre les options.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Fonction</th>
<th>Comment l’effectuer</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Fermer</p></td>
<td><p>Ferme votre affichage Lync, mais laisse s’exécuter la session Lync identifiée avec votre ID d’utilisateur. Cela vous permet de continuer à recevoir des notifications et d’interagir avec d’autres personnes.</p>
<p>Vous pouvez rétablir l’affichage à tout moment en cliquant sur l’icône Lync dans la barre des tâches ou dans la zone de notification en bas de l’écran.</p></td>
<td><p>Dans la fenêtre principale Lync, effectuez l’une des opérations suivantes :</p>
<ol>
<li><p>Sélectionnez le bouton <strong>options</strong> , puis sélectionnez <strong>fichier</strong> &gt; <strong>Fermer</strong>.</p></li>
<li><p>Cliquez sur le bouton <strong>Fermer</strong> (X) dans le coin supérieur droit de la fenêtre.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>Se déconnecter</p></td>
<td><p>Met fin à la session Lync associée à votre ID d’utilisateur, mais Lync continue de s’exécuter en arrière-plan. Lorsque vous vous déconnectez, la fenêtre de connexion s’affiche.</p>
<div>

> [!TIP]  
> Sélectionnez <STRONG>Supprimer mes informations de connexion</STRONG> lorsque vous vous déconnectez pour supprimer l’enregistrement de votre ID de connexion et de votre mot de passe de l’ordinateur. En procédant ainsi, il peut être plus facile pour les utilisateurs de la prise en charge de résoudre les problèmes de connexion. Vous pouvez également vous assurer que vos informations de connexion sont plus sécurisées en rendant les utilisateurs non autorisés difficiles à se connecter avec vos informations d’identification.


</div></td>
<td><p>Dans la fenêtre principale Lync <strong>, sélectionnez le</strong> bouton <strong>options</strong> , puis &gt; <strong>déconnectez-vous</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Quitter</p></td>
<td><p>Termine votre session Lync et arrête Lync sur votre ordinateur. Une fois la sortie terminée, si vous voulez redémarrer Lync, sélectionnez <strong>Démarrer</strong> &gt; <strong>tous les programmes</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</p></td>
<td><p>Dans la fenêtre principale Lync, sélectionnez le bouton <strong>options</strong> , <strong>puis sélectionnez</strong> &gt; <strong>quitter</strong>.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>Se connecter à Lync à l’aide d’une carte à puce

Certaines organisations utilisent désormais un processus de connexion en plusieurs étapes, appelé authentification à deux facteurs, pour renforcer la sécurité de leurs utilisateurs Lync 2013. Si vous envisagez d’utiliser cette option, vous aurez besoin d’une « carte à puce » pour vous connecter à Lync. Les cartes à puce sont de deux types, physiques et virtuels :

  - **Physique**     La taille d’une carte de crédit. Vous l’insérez dans un lecteur de carte à puce lorsque vous vous connectez.

  - **Virtuel**     N’est pas un objet physique, mais un identificateur électronique qui est écrit sur une puce spéciale sur votre ordinateur, qui, par essence, crée la carte à puce sur votre ordinateur. Disponible uniquement pour les ordinateurs Windows 8 qui contiennent le processeur TPM (Trusted Platform Module).

<div>

## <a name="enroll-your-smart-card"></a>Inscrire votre carte à puce

Avant de pouvoir vous connecter avec une carte à puce, la carte doit être « inscrite », c’est-à-dire que vos informations d’identification utilisateur doivent être identifiées avec la carte. C’est le cas si la carte est physique ou virtuelle. Ce processus a peut-être déjà été effectué par votre administrateur Lync Server. Vérifiez avec eux si vous ne savez pas si cela a été fait.

<div>


> [!NOTE]  
> Étant donné que chaque carte à puce virtuelle est associée uniquement au périphérique sur lequel elle est installée, une carte distincte doit être entrée pour chaque ordinateur Windows 8 que vous utilisez.



</div>

**Pour inscrire manuellement votre carte à puce**

1.  Ouvrez une session sur l’ordinateur sur lequel vous exécuterez Lync.

2.  À l’aide d’Internet Explorer, accédez à la page d’inscriptions Web de l’autorité de certification de votre organisation.
    
    Demandez à votre administrateur Lync Server l’adresse Web de cette ressource si vous ne l’avez pas déjà fait. L’URL se présente comme suit : https://MyCA.\ [yourcompanyname \] . com/certsrv.
    
    <div>
    

    > [!NOTE]  
    > Si vous utilisez Internet Explorer 10, vous devrez peut-être afficher ce site Web en mode de compatibilité.

    
    </div>

3.  Lorsque vous êtes invité à vous connecter à la page de certification, ouvrez une session à l’aide de votre compte de domaine (plutôt que en tant qu’administrateur de votre ordinateur).

4.  Sur la page d’accueil du site Web, sélectionnez **demander un certificat**.

5.  Sélectionnez **demande avancée**.

6.  Sélectionnez **créer et envoyer une demande auprès de cette autorité de certification**, puis cliquez sur **suivant**.

7.  Vous verrez maintenant une page appelée station d’enregistrement de carte à puce. Approuvez la demande d’installation du contrôle ActiveX, puis complétez le formulaire de demande de certificat avancée comme suit :
    
    1.  Sélectionnez **utilisateur de carte à puce** dans la liste déroulante **modèle de certificat** .
    
    2.  Sélectionnez **créer un nouveau jeu de clés**.
    
    3.  Recherchez les informations du fabricant sur l’étiquette de votre carte à puce et sélectionnez ce fabricant dans la liste déroulante **CSP** .
    
    4.  Sélectionnez **CSP** comme format de demande, s’il n’est pas déjà sélectionné.
    
    5.  Sélectionnez **SHA1** dans la liste déroulante algorithme de hachage, si ce n’est déjà fait.
    
    6.  Donnez un nom que vous reconnaîtrez à votre certificat, puis cliquez sur **Envoyer**.

8.  À présent, insérez votre carte à puce vierge dans le lecteur de carte connecté à la station d’inscription et cliquez sur **inscrire**.

9.  Lorsque vous y êtes invité, entrez votre code confidentiel (PIN), puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Si le support technique ne vous a pas fourni de code confidentiel spécial pour inscrire votre carte à puce, utilisez la valeur de code confidentiel par défaut de la carte à puce, qui est 12345678.

    
    </div>

10. Sélectionnez l’option obliger l’utilisateur (vous) à modifier le code confidentiel la première fois que la carte à puce est utilisée.

11. À présent, insérez votre carte à puce vierge dans le lecteur de carte connecté à la station d’inscription et cliquez sur **inscrire**.

12. Lorsque vous y êtes invité, entrez votre code confidentiel (PIN), puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Si le support technique ne vous a pas fourni de code confidentiel spécial pour inscrire votre carte à puce, utilisez la valeur de code confidentiel par défaut de la carte à puce, qui est 12345678.

    
    </div>

13. Sélectionnez l’option obliger l’utilisateur (vous) à modifier le code confidentiel la première fois que la carte à puce est utilisée.

14. Cliquez sur **OK** pour confirmer que le certificat affiché contient vos informations.

15. Une fois que vous voyez le message indiquant que le certificat a été émis, cliquez sur **installer ce certificat** pour terminer le processus d’enregistrement.

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>Se connecter à Lync avec vos informations d’identification de carte à puce

Avant d’utiliser votre carte à puce pour la première fois, il est recommandé de cliquer sur **Supprimer mes informations de connexion** sur la page de connexion à Lync. Cette opération efface toutes les informations d’identification de connexion stockées sur votre ordinateur et élimine une source d’erreur possible.

**Pour vous connecter à Lync avec vos informations d’identification de carte à puce**

1.  Démarrez le client Lync.

2.  Sur l’écran de connexion, tapez votre nom de compte d’utilisateur de connexion dans la zone **adresse de connexion** , puis cliquez sur **se connecter**.

3.  Si vous utilisez une carte à puce virtuelle, ignorez cette étape.
    
    Si vous utilisez une carte à puce physique, insérez la carte à puce dans votre lecteur de carte à puce et vous y êtes invité, puis cliquez sur **OK** lors de la détection de la carte.

4.  Tapez le code confidentiel de votre carte à puce, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Si vous n’avez pas attribué de numéro de code confidentiel à une carte à puce par votre personne du support technique, utilisez la valeur par défaut, qui est 12345678.

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

