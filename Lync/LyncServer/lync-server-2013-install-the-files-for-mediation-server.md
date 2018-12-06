---
title: 'Lync Server 2013 : Installation des fichiers du serveur de médiation'
TOCTitle: Installation des fichiers du serveur de médiation
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412998(v=OCS.15)
ms:contentKeyID: 49299312
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation des fichiers du serveur de médiation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-08-06_

Pour mener à bien cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et utilisateur de domaine appartenant au moins au groupe RTCUniversalReadOnlyAdmins.

Utilisez la procédure décrite dans cette rubrique pour exécuter l’Assistant Déploiement Lync Server 2013 pour installer les fichiers pour le serveur de médiation sur un ordinateur que vous avez ajouté à un pool de serveurs de médiation lorsque vous avez utilisé le générateur de topologie pour définir et publier le pool. Lors de l’installation des fichiers pour le serveur de médiation, vous devez également installer et affecter le certificat requis par chaque ordinateur dans un pool de serveurs de médiation.

Sur ce site, si vous avez déjà déployé des serveurs de médiation colocalisés sur les pools de serveurs frontaux ou le serveur Standard Edition, vous pouvez ignorer cette rubrique et passer directement à [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md).

> [!NOTE]  
> Cette rubrique suppose que vous ayez déjà défini et publié un pool de serveurs de médiation autonome tel que décrit dans <a href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Définition d’un serveur de médiation dans le générateur de topologie dans Lync Server 2013</a> et <a href="lync-server-2013-publish-the-topology.md">Publication de la topologie dans Lync Server 2013</a> dans la documentation de déploiement, et que vous ayez vérifié que les ordinateurs du pool de serveurs de médiation répondent aux exigences décrites dans <a href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Configuration logicielle requise pour Entreprise Voix dans Lync Server 2013</a> and <a href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Conditions prérequises de configuration et de sécurité pour Voix Entreprise dans Lync Server 2013</a>.

## Pour installer les fichiers sur un pool de serveurs de médiation autonome

1.  Dans le support d’installation, cliquez avec le bouton droit sur *\<support d’installation\>* **\\Setup\\amd64\\Setup.exe** , puis cliquez sur **Exécuter en tant qu’administrateur** .

2.  On the **Installation Location** page, click **OK**.

3.  Dans la page **Contrat de Licence Utilisateur Final** , cliquez sur **J’accepte** , puis sur **OK** . (Cette étape est nécessaire pour continuer.)

4.  Dans la page **Assistant Déploiement Lync Server 2010** , cliquez sur **Installer ou mettre à jour le système Lync Server** .

5.  À l’**Étape 1 : installer le magasin de configuration local** , cliquez sur **Exécuter** , puis suivez les instructions affichées à l’écran.

6.  Dans la page **Configurer un réplica local du magasin central de gestion** , acceptez le paramètre par défaut **Récupérer directement depuis le magasin central de gestion** , puis cliquez sur **Suivant** .

7.  Dans la page **Exécution de commandes** , lorsque le statut de la tâche est **Terminé** , cliquez sur **Terminer** .

8.  À l’**Étape 2 : installer ou supprimer des composants Lync Server** , cliquez sur **Exécuter** , puis sur **Suivant** .

9.  Dans la page **Exécution de commandes** , lorsque le statut de la tâche est **Terminé** , cliquez sur **Terminer** .

10. À l’**Étape 3 :Demander, installer ou affecter les certificats** , cliquez sur **Exécuter** . Suivez les instructions qui s’affichent à l’écran, en acceptant les paramètres par défaut. Le serveur de médiation nécessite un certificat. Vous devrez donc répéter deux fois l’**Étape 3**  : une fois pour émettre le certificat requis, une autre pour l’affecter.

11. Une fois le certificat émis et attribué, à l’**Étape 4: démarrer les services** , cliquez sur **Exécuter** , puis suivez les instructions affichées à l’écran.

12. Une fois l’**Étape 4** terminée, redémarrez le serveur et connectez-vous-y en tant que membre du groupe DomainAdmins.

13. Sur l’ordinateur exécutant le Panneau de configuration Lync Server, vérifiez sur la page **Topologie** du Panneau de configuration Lync Server que le statut du service du serveur de médiation est représenté par une coche verte. Si une croix rouge est affichée, sélectionnez le serveur de médiation. Dans le menu **Action** , cliquez sur **Démarrer tous les services** .

Si vous avez ajouté plusieurs ordinateurs au pool de serveurs de médiation, effectuez cette procédure sur tous les ordinateurs du pool de serveurs de médiation. Si vous n’avez pas besoin d’installer de fichiers pour le serveur de médiation sur d’autres ordinateurs, suivez les procédures décrites dans [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md) pour configurer les paramètres de connexion des jonctions entre ce pool de serveurs de médiation (ou tous les serveurs de médiation sur ce site) et son homologue.

## Voir aussi

#### Concepts

[Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

