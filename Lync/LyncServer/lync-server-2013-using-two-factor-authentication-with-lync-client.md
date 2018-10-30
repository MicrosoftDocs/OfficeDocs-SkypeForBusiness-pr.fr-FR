---
title: Utilisation de l’authentification à deux facteurs avec le client Lync
TOCTitle: Utilisation de l’authentification à deux facteurs avec le client Lync
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn338071(v=OCS.15)
ms:contentKeyID: 56269659
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation de l’authentification à deux facteurs avec le client Lync

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette rubrique décrit l’utilisation de l’authentification à deux facteurs avec le client Lync 2013.

## Se connecter à Lync 2013 pour la première fois

Vos informations de connexion Lync sont configurées automatiquement lorsque Lync 2013 est installé. Il se peut que vous deviez démarrer le client Lync manuellement la première fois que vous utilisez Lync.

**Pour se connecter à Lync 2013 pour la première fois**

1.  Connectez-vous au réseau de votre organisation.

2.  Sélectionnez **Démarrer** \> **Tous les programmes** \> **Microsoft Lync \> Lync 2013**.
    
    L’écran de connexion de Lync doit apparaître.
    
      - Si la zone Adresse de connexion est déjà renseignée, confirmez que l’adresse affichée est correcte.
    
      - Si elle n’est pas correcte ou si la zone est vide, entrez votre adresse de connexion Lync (il s’agit généralement de votre adresse de messagerie).
    
      - Si une zone Mot de passe vide est affichée, ajoutez votre mot de passe.

3.  Sélectionnez **Se connecter**.

## Se déconnecter de Lync

Lorsque vous avez terminé d’utiliser Lync, vous pouvez fermer la fenêtre, vous déconnecter de votre session ou quitter le programme via le menu Fichier. Le tableau suivant décrit les différences entre les diverses options.


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
<td><p>Ferme la fenêtre Lync sans fermer votre session Lync identifiée avec votre ID d’utilisateur. Ceci vous permet de continuer à recevoir des notifications et à interagir avec les autres utilisateurs.</p>
<p>Vous pouvez afficher la fenêtre à nouveau à tout moment en cliquant sur l’icône Lync dans la barre des tâches ou la zone de notification au bas de l’écran.</p></td>
<td><p>Dans la fenêtre principale de Lync, effectuez l’une des opérations suivantes :</p><ol><li><p>Sélectionnez le bouton <strong>Options</strong>, puis <strong>Fichier</strong> &gt; <strong>Fermer</strong>.</p></li>
> <li><p>Cliquez sur le bouton <strong>Fermer</strong> (X) dans le coin supérieur droit de la fenêtre.</p></li></ol></td>
</tr>
<tr class="even">
<td><p>Se déconnecter</p></td>
<td><p>Met fin à la session Lync associée à votre ID d’utilisateur. Lync continue toutefois d’être exécuté en arrière-plan. Lorsque vous vous déconnectez, la fenêtre de connexion apparaît.</p>
<div>

> [!TIP]  
> Sélectionnez <strong>Supprimer mes informations de connexion</strong> lorsque vous vous déconnectez pour supprimer l’enregistrement de vos ID de connexion et mot de passe de l’ordinateur. Cela peut simplifier la résolution des problèmes de connexion pour les agents de support technique. Vos informations de connexion bénéficient d’une sécurité accrue en rendant plus difficile la connexion d’utilisateurs non autorisés à l’aide de vos informations d’identification.
</div></td>
<td><p>Dans la fenêtre principale de Lync, sélectionnez le bouton <strong>Options</strong>, puis <strong>Fichier</strong> &gt; <strong>Se déconnecter</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Quitter</p></td>
<td><p>Met fin à votre session Lync et arrête Lync sur votre ordinateur. Une fois que vous avez quitté le programme, si vous voulez redémarrer Lync, sélectionnez <strong>Démarrer</strong> &gt; <strong>Tous les programmes</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</p></td>
<td><p>Dans la fenêtre principale de Lync, sélectionnez le bouton <strong>Options</strong>, puis <strong>Fichier</strong> &gt; <strong>Quitter</strong>.</p></td>
</tr>
</tbody>
</table>


## Se connecter à Lync avec une carte à puce

Certaines organisations utilisent désormais un processus de connexion en plusieurs étapes (authentification multifacteur) pour accroître la sécurité des utilisateurs de Lync 2013. Si vous devez utiliser cette option, vous avez besoin d’une « carte à puce » pour vous connecter à Lync. Il existe deux sortes de carte à puce (physique et virtuelle) :

  - **Carte à puce physique**   Environ la taille d’une carte de crédit. Vous devez l’insérer dans un lecteur de cartes à puce lorsque vous vous connectez.

  - **Carte à puce virtuelle**   Il ne s’agit pas d’un objet physique mais d’un identifiant électronique écrit sur une puce spéciale sur votre ordinateur. Celle-ci est chargée de créer la carte à puce dans votre ordinateur. Ce type de carte peut seulement être utilisé avec les ordinateurs Windows 8 contenant une puce de module de plateforme sécurisée.

## Inscrire votre carte à puce

Avant de vous connecter avec une carte à puce, celle-ci doit être « inscrite » (vos informations d’identification doivent être identifiées auprès de la carte), que la carte soit virtuelle ou physique. Il est possible que votre administrateur Lync Server ait déjà effectué cette opération. Contactez-le si vous n’êtes pas certain que ce soit le cas.

> [!NOTE]  
> Chaque carte à puce virtuelle étant seulement associée à l’appareil sur lequel elle est installée, une nouvelle carte doit être inscrite pour chaque ordinateur Windows 8 que vous utilisez.

**Pour inscrire votre carte à puce manuellement**

1.  Connectez-vous à l’ordinateur sur lequel vous exécuterez Lync.

2.  À l’aide d’Internet Explorer, accédez à la page d’inscription de l’autorité de certification via le web de votre organisation.
    
    Demandez à votre administrateur Lync Server l’adresse web de cette ressource si vous ne l’avez pas déjà. L’URL est semblable à celle-ci : https://MyCA.\[nom de votre entreprise\].com/certsrv.
    
    > [!NOTE]  
    > Si vous utilisez Internet Explorer 10, vous devrez peut être afficher ce site web en mode de compatibilité.

3.  Lorsque vous y êtes invité sur la page de certification, connectez-vous à l’aide de votre compte de domaine (plutôt qu’avec un compte d’administrateur de votre ordinateur).

4.  Dans la page Bienvenue du site web, sélectionnez **Demander un certificat**.

5.  Sélectionnez **Demande avancée**.

6.  Sélectionnez **Créer et soumettre une demande de requête auprès de cette autorité de certification**, puis cliquez sur **Suivant**.

7.  La page Station d’inscription de carte à puce Microsoft apparaît. Acceptez la demande d’installation du contrôle ActiveX, puis complétez l’écran Demande de certificat avancée comme suit :
    
    1.  Sélectionnez **Utilisateur de carte à puce** dans la liste déroulante **Modèle de certificat**.
    
    2.  Sélectionnez **Créer un nouveau jeu de clés**.
    
    3.  Recherchez les informations relatives au fabricant sur l’étiquette de votre carte à puce, puis sélectionnez le fabricant dans la liste déroulante **Fournisseur de services de chiffrement**.
    
    4.  Sélectionnez **Fournisseur de services de chiffrement** comme format de la demande, si cette option n’est pas déjà sélectionnée.
    
    5.  Dans la liste déroulante Algorithme de hachage, sélectionnez **sha1** si cette option n’est pas déjà sélectionnée.
    
    6.  Donnez un nom reconnaissable à votre certificat, puis cliquez sur **Envoyer**.

8.  Insérez votre carte à puce vierge dans le lecteur de cartes relié à la station d’inscription, puis cliquez sur **Inscrire**.

9.  Lorsque vous y êtes invité, entrez votre code confidentiel, puis cliquez sur **OK**.
    
    > [!NOTE]  
    > Si votre agent de support technique ne vous a pas communiqué de code confidentiel spécial pour inscrire votre carte à puce, utilisez la valeur de code confidentiel par défaut de la carte à puce (12345678).

10. Sélectionnez l’option forçant l’utilisateur (vous) à modifier le code confidentiel à la première utilisation de la carte.

11. Insérez votre carte à puce vierge dans le lecteur de cartes relié à la station d’inscription, puis cliquez sur **Inscrire**.

12. Lorsque vous y êtes invité, entrez votre code confidentiel, puis cliquez sur **OK**.
    
    > [!NOTE]  
    > Si votre agent de support technique ne vous a pas communiqué de code confidentiel spécial pour inscrire votre carte à puce, utilisez la valeur de code confidentiel par défaut de la carte à puce (12345678).

13. Sélectionnez l’option forçant l’utilisateur (vous) à modifier le code confidentiel à la première utilisation de la carte.

14. Cliquez sur **OK** pour confirmer que le certificat affiché inclut vos informations.

15. Une fois que vous recevez l’avis confirmant l’émission du certificat, cliquez sur **Installer ce certificat** pour finaliser le processus d’inscription.

## Se connecter à Lync avec les informations d’identification de votre carte à puce

Avant d’utiliser votre carte à puce la première fois, il est recommandé de cliquer sur **Supprimer mes informations de connexion** dans la page de connexion à Lync. Ceci permet de supprimer les informations d’identification de connexion stockées sur votre ordinateur et d’éliminer une source possible d’erreur.

**Pour vous connecter à Lync avec les informations d’identification de votre carte à puce**

1.  Démarrez le client Lync.

2.  Dans l’écran Se connecter, tapez le nom de compte d’utilisateur de connexion dans la zone **Adresse de connexion**, puis cliquez sur **Se connecter**.

3.  Si vous utilisez une carte à puce virtuelle, ignorez cette étape.
    
    Si vous utilisez une carte à puce physique, insérez la carte à puce dans votre lecteur de cartes à puce, puis lorsque vous y êtes invité, cliquez sur **OK** lorsque la carte est détectée.

4.  Tapez le code confidentiel de votre carte à puce, puis cliquez sur **OK**.
    
    > [!NOTE]  
    > Si votre agent de support technique ne vous a pas communiqué de code confidentiel, utilisez la valeur par défaut (12345678).
