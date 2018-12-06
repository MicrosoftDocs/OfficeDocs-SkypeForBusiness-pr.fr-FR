---
title: "Lync Server 2013 : Publi. d’Office Web Apps Server avec un serv. proxy inverse"
TOCTitle: Publication d’Office Web Apps Server avec un serveur proxy inverse
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204665(v=OCS.15)
ms:contentKeyID: 49296218
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publication d’Office Web Apps Server dans Lync Server 2013 avec un serveur proxy inverse

 

_**Dernière rubrique modifiée :** 2013-02-25_

Si vous souhaitez que les utilisateurs externes (c’est-à-dire, les utilisateurs qui se connectent depuis l’extérieur du pare-feu de votre organisation) aient accès aux présentations PowerPoint d’Office Web Apps Server, vous devez utiliser Office Web Apps Server et un serveur de proxy inverse tel que Microsoft Forefront Threat Management Gateway. Vous devez également créer et configurer une règle de publication de site web ; cette règle permet aux utilisateurs de se connecter au serveur. Si vous n’avez pas besoin d’autoriser l’accès à des utilisateurs externes, vous n’avez pas besoin de configurer une telle règle.

Pour configurer une règle de publication de site web dans Forefront Threat Management Gateway, procédez comme suit :

1.  Cliquez sur **Démarrer** , sur **Tous les programmes** , sur **Microsoft Forefront TMG** , puis sur **Forefront TMG Management** .

2.  Dans Forefront TMG, cliquez avec le bouton droit sur **Stratégie de pare-feu** , pointez sur **Nouveau** , puis cliquez sur **Règle de publication de site web** .

3.  Dans l’Assistant Nouvelle règle de publication web, dans la page **Bienvenue dans l’Assistant Nouvelle règle de publication web** , tapez le nom de votre nouvelle règle dans la zone **Nom de la règle de publication web** (par exemple, **Règle Office Web Apps Server** ), puis cliquez sur **Suivant** .

4.  Dans la page **Spécifier l’action de la règle** , sélectionnez **Autoriser** , puis cliquez sur **Suivant** .

5.  Dans la page **Type de publication** , sélectionnez **Publier un seul site web ou équilibreur de charge** , puis cliquez sur **Suivant** .

6.  Dans la page **Sécurité de connexion serveur** , sélectionnez **Utiliser SSL pour se connecter au serveur web publié ou à la batterie de serveurs** , puis cliquez sur **Suivant** .

7.  Dans la page **Détails de la publication interne** , tapez le nom de domaine complet du serveur Office Web Apps (par exemple, **officewebapps01.contoso.com** ) dans la zone **Nom de site local** , puis cliquez sur **Suivant** . Le nom entré dans la zone **Nom de site local** doit figurer dans le champ Sujet ou le champ Autre nom du sujet du certificat que vous avez affecté à Office Web Apps Server.

8.  Dans la page **Détails de la publication interne** , tapez **/\*** dans la zone **Chemin d’accès (facultatif)** , puis cliquez sur **Suivant** . La syntaxe /\* garantit que tous les dossiers et sous-dossiers pour le site sont publiés.

9.  Dans la page **Informations sur les noms publics** , sélectionnez **Ce nom de domaine (saisissez ci-dessous)** dans la zone déroulante **Accepter les demandes pour** , puis tapez le nom complet de votre serveur Office Web Apps Server dans la zone de nom public. Ce nom doit être le même que le nom utilisé pour accéder à votre site web. Par exemple, si pour accéder à votre site, il faut utiliser l’URL http://officewebapps01.contoso.com, vous devez alors entrer **officewebapps01.contoso.com** dans la zone **Nom public** .

10. Cliquez sur **Suivant** .

11. Dans la page **Sélectionnez le port d’écoute** , cliquez sur **Nouveau** .

12. Dans l’Assistant Nouvelle définition de port d’écoute web, tapez le nom du nouveau port d’écoute web (par exemple, **SSL** ) dans la zone **Nom du port d’écoute web** , puis cliquez sur **Suivant** .

13. Dans la page **Sécurité de la connexion cliente** , sélectionnez **Exiger les connexions sécurisées SSL avec les clients** , puis cliquez sur **Suivant** .

14. Dans la page **Adresses IP des ports d’écoute web** , sélectionnez **Externe** , sélectionnez **Interne** , puis cliquez sur **Suivant** .

15. Dans la page **Certificats SSL du port d’écoute** , sélectionnez **Utiliser un seul certificat pour ce port d’écoute web** , puis cliquez sur **Sélectionner le certificat** .

16. Dans la boîte de dialogue **Sélectionner le certificat** , sélectionnez le certificat à utiliser pour ce port d’écoute web, puis cliquez sur **Sélectionner** .

17. Dans la page **Certificats SSL du port d’écoute** , cliquez sur **Suivant** .

18. Dans la page **Paramètres d’authentification** , sélectionnez **Aucune authentification** dans la liste déroulante **Sélectionner la méthode avec laquelle les clients fourniront les informations d’identification à Forefront TMG** , puis cliquez sur **Suivant** .

19. Dans la page **Paramètres de l’authentification unique** , cliquez sur **Suivant** .

20. Dans la page **Fin de l’Assistant Nouveau port d’écoute web** , vérifiez le résumé de vos choix de configuration. Lorsque c’est fait, cliquez sur **Terminer** .

21. Dans la page **Sélectionnez le port d’écoute** , cliquez sur **Suivant** .

22. Dans la page **Délégation de l’authentification** , sélectionnez **Aucune délégation, mais le client peut s’authentifier directement** dans la liste déroulante **Sélectionner la méthode utilisée par Forefront TMG pour s’authentifier auprès du serveur web publié** , puis cliquez sur **Suivant** .

23. Dans la page **Ensembles d’utilisateurs** , confirmez que les ensembles d’utilisateurs appropriés sont répertoriés. Par défaut, il s’agit de l’ensemble d’utilisateurs **Tous les utilisateurs** . Cliquez sur **Ajouter** pour ajouter les autres ensembles d’utilisateurs que vous avez éventuellement définis. Lorsque c’est fait, cliquez sur **Suivant** .

24. Dans la page **Fin de l’Assistant Nouvelle règle de publication web** , cliquez sur **Terminer** .

Si vous cliquez sur **Terminer** , cela ne signifie pas que vous avez terminé la procédure ; en d’autres termes, la nouvelle règle n’est pas automatiquement appliquée. En fait, vous devez cliquer sur le bouton **Appliquer** qui s’affiche dans l’interface utilisateur de Forefront TMG. Lorsque vous cliquez sur **Appliquer** , la boîte de dialogue **Description de la modification de la configuration** s’affiche. Cliquez sur **Appliquer** dans cette boîte de dialogue pour activer la nouvelle règle de publication.

Une fois que votre nouvelle règle a été appliquée, vous devez y apporter quelques modifications mineures pour que les utilisateurs puissent utiliser les fonctionnalités de présentation PowerPoint. Pour cela, procédez comme suit :

1.  Dans Forefront TMG, cliquez avec le bouton droit sur le nom de la nouvelle règle de publication, puis cliquez sur **Propriétés** .

2.  Dans la boîte de dialogue **Propriétés** , sous l’onglet **À** , sélectionnez l’option **Transmettre l’en-tête de l’hôte d’origine plutôt que l’en-tête réel** .

3.  Sous l’onglet **Trafic** , cliquez sur **Filtrage** , puis sur **Configurer HTTP** .

4.  Dans la boîte de dialogue **Configuration de la stratégie HTTP pour la règle** , désactivez la case à cocher **Vérifier la normalisation** , puis cliquez sur **OK** .

5.  Dans la boîte de dialogue **Propriétés** , cliquez sur **OK** .

6.  Dans Forefront TMG, cliquez sur **Appliquer** pour appliquer les modifications. Lorsque la boîte de dialogue **Description de la modification de la configuration** s’affiche, cliquez sur **Appliquer** .

Après avoir effectué l’installation, vous pouvez tester Office Web Apps Server à l’aide des procédures indiquées dans la rubrique [Validation de la configuration d’Office Web Apps Server dans Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).

