---
title: 'Lync Server 2013 : Configuration des certificats pour les serveurs'
TOCTitle: Configuration des certificats pour les serveurs
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398995(v=OCS.15)
ms:contentKeyID: 49299115
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des certificats pour les serveurs dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour effectuer cette procédure, vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins ou disposer des autorisations déléguées correctes. Pour plus d’informations sur la délégation d’autorisations, reportez-vous à [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). En fonction de votre entreprise et des besoins en matière de certificats, il se peut que vous deviez appartenir à d’autres groupes. Contactez le groupe chargé de gérer l’autorité de certification de votre infrastructure de clés publiques.

> [!NOTE]  
> Lync Server 2013 prend en charge la suite SHA-2 (SHA-2 utilise les longueurs de hachage de 224, 256, 384 et 512 bits) d’algorithmes de hachage et de signature pour les connexions à partir de clients exécutant les systèmes d’exploitation Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista ou Windows XP, en plus de Lync Phone Edition. Pour permettre la prise en charge de l’accès externe via la suite SHA-2, le certificat externe est émis par une autorité de certification publique pouvant également émettre un certificat avec le même hachage de longueur en bits.

> [!CAUTION]  
> La sélection de l’algorithme de hachage et de signature dépend des clients et serveurs qui utiliseront le certificat, et des autres ordinateurs et appareils avec lesquels les clients et serveurs communiqueront, lesquels doivent également savoir comment utiliser les algorithmes définis dans le certificat. Pour plus d’informations sur les longueurs de hachage prises en charge dans le système d’exploitation et certaines applications clientes, reportez-vous à <a href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</a>.

Chaque serveur Standard Edition ou serveur frontal nécessite jusqu’à quatre certificats : le certificat de l’émetteur de jetons OAuth, un certificat par défaut, un certificat interne web et un certificat externe web. Cependant, il est possible de demander et d’attribuer un certificat par défaut unique contenant les entrées de noms d’objet appropriées ainsi que le certificat de l’émetteur de jetons OAuth. Pour plus d’informations sur les certificats requis, reportez-vous à [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) (contenu éventuellement en anglais). Pour plus d’informations sur la demande, l’attribution et l’installation du certificat de l’émetteur de jetons OAuth, reportez-vous à [Gestion de l’authentification serveur à serveur (Oauth) et des applications partenaires dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) (contenu éventuellement en anglais).

Utilisez la procédure suivante pour demander, attribuer et installer les certificats serveur Standard Edition ou serveur frontal. Répétez la procédure pour chaque serveur frontal.

> [!IMPORTANT]  
> La procédure suivante décrit la configuration des certificats à partir d’une infrastructure à clé publique (PKI) d’entreprise interne déployée par votre entreprise et avec un traitement hors ligne de la demande. Pour plus d’informations sur l’obtention de certificats à partir d’une autorité de certification publique, reportez-vous à <a href="lync-server-2013-certificate-requirements-for-internal-servers.md">Exigences de certificat pour les serveurs internes dans Lync Server 2013</a> (contenu éventuellement en anglais) dans la documentation de planification. Cette procédure décrit également comment demander, affecter et installer les certificats lors de la configuration du serveur frontal. Si vous avez demandé des certificats par avance comme décrit à la section <a href="lync-server-2013-request-certificates-in-advance-optional.md">Demande des certificats à l’avance (facultatif) pour Lync Server 2013</a> de la documentation de déploiement, ou si vous n’utilisez pas la PKI d’entreprise interne déployée dans votre entreprise pour obtenir des certificats, vous devez modifier cette procédure en conséquence.

## Pour configurer des certificats pour un serveur frontal

1.  Dans l’Assistant Déploiement de Lync Server, cliquez sur **Exécuter** en regard de **Étape 3 : Demander, installer ou attribuer des certificats** .

2.  Dans la page **Assistant Certificat** , cliquez sur **Demander** .

3.  Dans la page **Demande de certificat** , cliquez sur **Suivant** .

4.  Dans la page **Demandes différées ou immédiates** , vous pouvez accepter l’option par défaut **Envoyer la demande immédiatement à une autorité de certification en ligne** en cliquant sur **Suivant** . L’autorité de certification interne avec inscription en ligne automatique doit être disponible si vous sélectionnez cette option. Si vous choisissez de mettre la demande en attente, vous serez invité à indiquer un nom et un emplacement pour enregistrer le fichier de demande de certificat. La demande de certificat doit être présentée et traitée par une autorité de certification interne à votre entreprise ou publique. Vous devrez ensuite importer la réponse du certificat et lui attribuer le rôle approprié.

5.  Dans la page **Sélectionnez une autorité de certification** , sélectionnez l’option **Sélectionner une autorité de certification dans la liste détectée pour votre environnement** , puis choisissez une autorité de certification connue (via un enregistrement dans les services de domaine Active Directory) dans la liste. Ou sélectionnez l’option **Spécifier une autre autorité de certification** , entrez le nom d’une autre autorité de certification dans la zone, puis cliquez sur **Suivant** .

6.  Dans la page **Compte d’autorité de certification** , vous êtes invité à saisir des informations d’identification pour demander et traiter la demande de certificat auprès de l’autorité de certification. Vous devez avoir déterminé si un nom d’utilisateur et un mot de passe sont nécessaires pour demander un certificat à l’avance. Votre administrateur de l’autorité de certification dispose des informations requises et peut vous assister pour cette étape. Si vous devez fournir des informations d’identification de remplacement, saisissez un nom d’utilisateur et un mot de passe dans les champs de texte, puis cliquez sur **Suivant** .

7.  Dans la page **Spécifier un autre modèle de certificat** , pour utiliser le modèle de serveur web par défaut, cliquez sur **Suivant** .
    
    > [!NOTE]  
    > Si votre entreprise a créé un modèle à employer en remplacement du modèle d’autorité de certification de serveur web, activez la case à cocher et entrez le nom du modèle de remplacement. Vous devez utiliser le nom du modèle défini par l’administrateur de l’autorité de certification.

8.  Dans la page **Nom et paramètres de sécurité** , spécifiez un **Nom convivial** devant vous permettre d’identifier le certificat et son utilisation. Si vous laissez ce champ vide, un nom est créé automatiquement. Définissez la **Longueur en bits** de la clé, ou acceptez la valeur par défaut de 2 048 bits. Sélectionnez l’option **Marquer la clé privée du certificat comme exportable** si vous estimez que le certificat et la clé privée doivent être déplacés ou copiés sur d’autres systèmes, puis cliquez sur **Suivant** .
    
    > [!NOTE]  
    > Lync Server 2013 présente des conditions minimales pour une clé privée exportable. L’un de ces emplacements concerne les serveurs Edge dans un pool, où le service d’authentification du serveur relais multimédia utilise des copies du certificat au lieu de plusieurs certificats individuels pour chaque instance du pool.

9.  Dans la page **Informations relatives à l’entreprise** , entrez éventuellement des informations sur l’entreprise, puis cliquez sur **Suivant** .

10. Dans la page **Informations géographiques** , entrez éventuellement des informations géographiques, puis cliquez sur **Suivant** .

11. Dans la page **Nom du sujet/Autres noms du sujet** , passez en revue les autres noms du sujet à ajouter, puis cliquez sur **Suivant** .

12. Dans la page **Paramètre du domaine SIP** , sélectionnez le **domaine SIP** , puis cliquez sur **Suivant** .

13. Dans la page **Configurer d’autres noms du sujet supplémentaires** , ajoutez d’éventuels noms de sujet supplémentaires requis, dont ceux nécessaires aux futurs domaines SIP supplémentaires, puis cliquez sur **Suivant** .

14. Dans la page **Résumé de la demande de certificat** , passez en revue les informations du résumé. Si les informations sont correctes, cliquez sur **Suivant** . Si vous devez corriger ou modifier un paramètre, cliquez sur **Précédent** pour revenir à la page correspondante afin d’y apporter la correction ou modification requise.

15. Dans la page **Exécution de commandes** , cliquez sur **Suivant** .

16. Dans la page **État de la demande de certificat en ligne** , passez en revue les informations affichées. Notez que le certificat a été émis et installé dans le magasin de certificats local. Si un message signale que le certificat a été émis et installé mais qu’il n’est pas valide, vérifiez que le certificat racine de l’autorité de certification a été installé dans le magasin Autorités de certification racines de confiance du serveur. Consultez la documentation de votre autorité de certification pour savoir comment extraire le certificat d’une autorité de certification racine de confiance. Si vous devez consulter le certificat extrait, cliquez sur **Afficher les détails du certificat** . Par défaut, la case à cocher **Attribuer ce certificat aux utilisations de certificat Lync Server** est activée. Si vous souhaitez attribuer manuellement le certificat, désactivez la case à cocher, puis cliquez sur **Terminer** .

17. Si vous avez désactivé la case à cocher **Attribuer ce certificat aux utilisations de certificat Lync Server** dans la page précédente, la page **Attribution de certificat** s’affiche. Cliquez sur **Suivant** .

18. Dans la page **Magasin de certificats** , sélectionnez le certificat que vous avez demandé. Si vous souhaitez afficher le certificat, cliquez sur **Afficher les détails du certificat** , puis sur **Suivant** pour continuer.
    
    > [!NOTE]  
    > Si la page <strong>État de la demande de certificat en ligne</strong> a signalé un problème de certificat, par exemple, que le certificat n’est pas valide, l’affichage du certificat réel peut vous aider à résoudre ce problème. Il existe deux problèmes spécifiques pouvant entraîner l’invalidité d’un certificat : il manque le certificat de l’autorité de certification racine de confiance indiqué ci-dessus et il manque une clé privée associée au certificat. Consultez la documentation de votre autorité de certification pour résoudre ces deux problèmes.

19. Dans la page **Résumé de l’attribution du certificat** , passez en revue les informations présentées pour vérifier qu’il s’agit bien du certificat à attribuer, puis cliquez sur **Suivant** .

20. Dans la page **Exécution de commandes** , passez en revue le résultat de la commande. Cliquez sur **Afficher le journal** si vous souhaitez consulter le processus d’attribution ou en cas d’erreur ou d’avertissement. Lorsque vous avez terminé votre vérification, cliquez sur **Terminer** .

21. Dans la page **Assistant Certificat** , vérifiez que l’option **État** du certificat affiche « Attribué », puis cliquez sur **Fermer** .

## Voir aussi

#### Autres ressources

[Configuration requise pour les infrastructures de certificat pour Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)

