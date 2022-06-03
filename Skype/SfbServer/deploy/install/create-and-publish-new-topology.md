---
title: Créer et publier une topologie dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 451c41a1-b8c5-4dc3-9e48-0da9ed5381a1
description: 'Résumé : Découvrez comment créer, publier et vérifier une nouvelle topologie avant d’installer Skype Entreprise Server.'
ms.openlocfilehash: 9ae6ee05a20f75946a87e611e972341094a11864
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860555"
---
# <a name="create-and-publish-new-topology-in-skype-for-business-server"></a>Créer et publier une topologie dans Skype Entreprise Server
 
**Résumé:** Découvrez comment créer, publier et vérifier une topologie avant d’installer Skype Entreprise Server.
  
Avant de pouvoir installer le système Skype Entreprise Server sur chacun des serveurs de la topologie, vous devez créer une topologie et la publier. Lorsque vous publiez une topologie, vous chargez les informations de topologie dans la base de données du Magasin central de gestion. S’il s’agit d’un pool Êdition Entreprise, vous créez la base de données du Magasin central de gestion la première fois que vous publiez une nouvelle topologie. Si c’est Édition Standard, vous devez exécuter le processus Préparer le premier serveur Édition Standard à partir de l’Assistant Déploiement avant de publier une topologie. Cela permet de préparer Édition Standard en installant une instance SQL Server Express Edition et en créant le magasin central de gestion. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez effectuer les étapes 6, 7 et 8 dans l’ordre, et après les étapes 1 à 5, comme indiqué dans le diagramme. La création et la publication d’une topologie sont décrites à l’étape 6 sur 8.
  
![Diagramme de vue d’ensemble.](../../media/c5c09ba2-c98b-4194-9857-7c3087c5560e.png)
  
## <a name="create-and-publish-new-topology"></a>Créer et publier une nouvelle topologie

Vous pouvez utiliser Skype Entreprise Server Générateur de topologie pour concevoir, définir, configurer et publier des topologies. Cet outil a été installé lorsque vous avez installé les outils d’administration plus haut dans l’article. Il existe de nombreux choix différents que vous pouvez faire lorsque vous créez une topologie. Dans cette procédure, vous allez créer une topologie de base avec conférence.
  
> [!IMPORTANT]
> Skype Entreprise Server nécessite SQL Server pour fonctionner. Les bases de données primaires sont connues sous le nom de Magasin central de gestion. Si vous déployez Êdition Entreprise, ces bases de données sont créées lorsque vous publiez la topologie en suivant les étapes ci-dessous. Dans ce cas, le Générateur de topologie vous demande les informations de connexion à une installation SQL Server. Si vous envisagez de déployer Édition Standard, vous devez installer SQL Server Express Edition avant de définir et de publier la nouvelle topologie. Pour installer SQL Server Express Edition, vous devez ouvrir l’Assistant Déploiement sur le serveur qui fera office de serveur frontal, puis exécuter Prepare First Édition Standard Server. Lorsque vous cliquez sur Préparer le premier serveur Édition Standard, l’Assistant Déploiement installe automatiquement SQL Server Express Edition et crée les bases de données du Magasin central de gestion. 
  
### <a name="create-a-new-topology"></a>Créer une topologie

1. Connectez-vous en tant qu’utilisateur standard ayant accès au Générateur de topologie.
    
2. Ouvrez Skype Entreprise Server Générateur de topologie.
    
3. Sélectionnez **Nouvelle topologie**, puis cliquez sur **OK**.
    
4. Sélectionnez un emplacement et un nom de fichier pour le fichier de configuration de topologie.
    
    > [!NOTE]
    > La configuration de la topologie est enregistrée en tant que fichier XML du Générateur de topologie (.tbxml). Lorsque vous publiez une topologie, vous envoyez (push) les informations de configuration du fichier à la base de données SQL Server. Lorsque vous ouvrez le Générateur de topologie à l’avenir, vous pouvez télécharger la configuration existante à partir de SQL Server directement dans topologie Builder et la publier dans SQL Server ou l’enregistrer en tant que fichier de configuration Du générateur de topologie. 
  
5. Dans **l’écran Définir le domaine principal**, entrez le **domaine SIP principal**, puis cliquez sur **Suivant**. Dans cet exemple, nous utilisons `contoso.local`, comme illustré dans la figure.
    
     ![Définissez le domaine sip principal.](../../media/353e6b38-485f-4042-8585-aefa6c74b554.png)
  
6. Ajoutez d’autres domaines SIP pris en charge, puis cliquez sur **Suivant**.
    
7. Entrez un **nom** et une **description** pour le premier site (emplacement), puis cliquez sur **Suivant**, comme illustré dans la figure.
    
     ![Définissez le premier site (emplacement).](../../media/d8b6c54a-2011-4efb-97fb-a4de0f11303c.png)
  
8. Entrez le code **ville**, **état/province** et **pays/région** du site, puis cliquez sur **Suivant**.
    
9. Cliquez sur **Terminer** pour terminer le processus de définition d’une nouvelle topologie. L’Assistant Nouveau front-end démarre automatiquement.
    
### <a name="define-a-front-end-pool-or-standard-edition-server"></a>Définir un pool frontal ou un serveur Édition Standard

1. Passez en revue les prérequis de l’Assistant, puis cliquez sur **Suivant**.
    
2. Entrez le nom de domaine complet (FQDN) du pool, sélectionnez **Êdition Entreprise pool frontal** ou **serveur Édition Standard**, puis cliquez sur **Suivant**, comme illustré dans la figure.
    
    > [!TIP]
    > Skype Entreprise Server Êdition Entreprise pouvez inclure plusieurs serveurs travaillant ensemble pour fournir le rôle frontal. Lorsque plusieurs serveurs sont utilisés pour remplir le rôle, il s’agit d’un pool. Ainsi, plusieurs serveurs travaillant ensemble pour fournir le rôle frontal sont également appelés le pool frontal. Skype Entreprise Server Édition Standard ne peut inclure qu’un seul serveur pour fournir le rôle frontal. Il est courant de faire référence au pool frontal même si un seul serveur fournit le rôle. 
  
     ![Définissez le pool frontal.](../../media/c1447557-261e-4260-a362-ab8d19070eb9.png)
  
3. Entrez les noms de domaine complets (FQDN) de tous les ordinateurs du pool, puis cliquez sur **Suivant** , comme indiqué dans la figure.
    
     ![Définissez les ordinateurs du pool.](../../media/1106b4f3-8745-485b-b495-f885a5dfefda.png)
  
4. Sélectionnez les fonctionnalités qui seront incluses dans cette topologie, puis cliquez sur **Suivant** , comme illustré dans la figure.
    
    > [!NOTE]
    > Skype Entreprise Server inclut de nombreuses fonctionnalités avancées. Passez en revue la documentation de planification et de déploiement pour chaque fonctionnalité spécifique que vous souhaitez utiliser. 
  
     ![Sélectionnez les fonctionnalités pour le déploiement.](../../media/77257588-d0e1-4517-a12a-869ffe009353.png)
  
5. Dans la page **Sélectionner les rôles serveur colocalisés** , vous pouvez choisir de colocaliser le serveur de médiation sur le serveur frontal, ou vous pouvez choisir de le déployer en tant que serveur autonome.
    
    Si vous envisagez de colocaliser le serveur de médiation sur le pool frontal Êdition Entreprise, vérifiez que la case à cocher est cochée. Les rôles serveur seront déployés sur les serveurs du pool. Si vous envisagez de déployer le serveur de médiation en tant que serveur autonome, désactivez la case à cocher appropriée. Vous allez déployer le serveur de médiation dans une étape de déploiement distincte après avoir déployé complètement le serveur frontal. Pour plus d’informations sur la planification d’une colocalisation, consultez [Les principes de base de la topologie pour Skype Entreprise Server](../../plan-your-deployment/topology-basics/topology-basics.md).
    
6. En utilisant la page **Associer des rôles serveur à cette page de pool frontal** , vous pouvez définir et associer des rôles serveur au pool frontal. Le rôle suivant est disponible :
    
    **Activer un pool Edge** Définit et associe un serveur Edge unique ou un pool de serveurs Edge. Un serveur Edge facilite la communication et la collaboration entre les utilisateurs de l’organisation et les personnes extérieures à l’organisation, y compris les utilisateurs fédérés.
    
    Il existe deux scénarios possibles que vous pouvez utiliser pour déployer et associer les rôles serveur.
    
    Dans le premier scénario, vous définissez une nouvelle topologie pour un nouvelle installation. Vous pouvez aborder l’installation de l’une des deux manières suivantes :
    
   - Désactivez la case à cocher et définissez la topologie. Une fois que vous avez publié, configuré et testé les rôles serveur frontal et serveur principal, vous pouvez réexécuter le Générateur de topologie pour ajouter les serveurs de rôles à la topologie. À l’aide de cette stratégie, vous pouvez tester le pool frontal et le serveur exécutant SQL Server sans complications supplémentaires liées à des rôles supplémentaires. Une fois que vous avez terminé votre test initial, vous pouvez réexécuter le Générateur de topologie pour sélectionner les rôles à déployer.
    
   - Sélectionnez les rôles à installer, puis configurez le matériel en fonction des rôles sélectionnés.
    
     Pour le scénario 2, vous disposez d’un déploiement existant et votre infrastructure est prête pour de nouveaux rôles, ou vous devez associer des rôles existants à un nouveau serveur frontal.
    
   - Dans ce cas, vous allez sélectionner les rôles que vous envisagez de déployer ou d’associer au nouveau serveur frontal. Dans les deux cas, vous devez définir les rôles, configurer le matériel nécessaire et effectuer l’installation.
    
7. Ensuite, vous allez définir le magasin SQL Server qui sera utilisé avec la topologie. Dans cet exemple, nous utilisons l’instance par défaut. Pour plus d’informations sur SQL Server fonctionnalités, telles que la haute disponibilité, consultez [Plan for high availability and disaster recovery in Skype Entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
    
   - Pour utiliser un magasin SQL Server qui a déjà été défini dans votre topologie, sélectionnez une instance dans **Magasin SQL**.
    
   - Pour définir une nouvelle instance SQL Server pour stocker les informations du pool, cliquez sur **Nouveau**, puis spécifiez le **nom** de domaine complet SQL Server dans la boîte de dialogue **Définir un nouveau SQL Store**.
    
   - Pour spécifier le nom d’une instance SQL Server, sélectionnez **Instance nommée**, puis spécifiez le nom de l’instance.
    
   - Pour utiliser l’instance par défaut, cliquez sur **Instance par défaut**.
    
   - Pour utiliser SQL mise en miroir, **sélectionnez Activer SQL mise en miroir**, puis sélectionnez une instance existante ou créez une instance.

     > [!NOTE]
     > SQL mise en miroir est disponible en Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de cluster de basculement AlwaysOn et les méthodes de clustering de basculement SQL sont préférés avec Skype Entreprise Server 2019.
    
     Pour cet exemple, nous allons entrer le **nom de domaine complet SQL Server**, configurer tous les paramètres de haute disponibilité pertinents, puis cliquer sur **OK**, comme illustré dans la figure.
    
     ![Créez un magasin SQL Server.](../../media/12822cf9-8608-43c0-94ce-2ca8b3a0ffd5.png)
  
8. Décidez si vous souhaitez activer SQL Server stocker la mise en miroir ou SQL Server témoin de mise en miroir, puis cliquez sur **Suivant**.
    
9. Définissez le partage de fichiers que vous souhaitez utiliser.
    
   - Pour utiliser un partage de fichiers qui a déjà été défini dans votre topologie, sélectionnez **Utiliser un partage de fichiers précédemment défini**.
    
   - Pour définir un nouveau partage de fichiers, sélectionnez **Définir un nouveau partage de fichiers**. Dans la zone **Nom de domaine complet du serveur de fichiers**, entrez le nom de domaine complet (FQDN) du serveur de fichiers existant où le partage de fichiers doit être placé, puis entrez un nom pour le partage de fichiers dans la zone **Partage de fichiers**.
    
     Pour cet exemple, nous allons cliquer sur **Définir un nouveau magasin de fichiers**, entrer le nom de domaine complet et le **partage de fichiers** du serveur de **fichiers**, puis cliquer sur **Suivant**.
    
     > [!NOTE]
     > Le partage de fichiers pour Skype Entreprise Server peut être colocalisé, mais il n’est pas recommandé pour des raisons de performances. Notez que dans cet exemple, le partage de fichiers a été localisé sur un serveur dédié unique qui servira de partage de fichiers. Toutefois, d’autres systèmes de partage de fichiers plus robustes, tels que DFS utilisant Windows Server 2012 R2, sont recommandés. Pour plus d’informations sur les systèmes de partage de fichiers pris en charge, consultez [Configuration requise pour votre environnement Skype Entreprise](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). Pour plus d’informations sur la création du partage de fichiers, consultez [Créer un partage de fichiers dans Skype Entreprise Server](create-a-file-share.md). Vous pouvez définir le partage de fichiers sans qu’il soit nécessaire de le créer. Vous devrez créer le partage de fichiers à l’emplacement que vous définissez avant de publier la topologie. 
  
10. Dans la page Spécifier l’URL des services web, vous devez décider si vous devez remplacer l’URL de base du pool de services Web interne. La raison de ce remplacement est liée à l’équilibrage de charge. Le trafic SIP de base peut être équilibré par le biais d’un simple équilibrage de charge DNS. Toutefois, le trafic réseau des services web HTTP/S doit utiliser une solution d’équilibrage de charge matérielle ou logicielle prise en charge. Pour les équilibreurs de charge pris en charge, consultez [Infrastructure for Skype Entreprise](../../../SfbPartnerCertification/certification/infra-gateways.md). Dans cet exemple, nous avons utilisé l’équilibrage de charge DNS pour le trafic SIP et une solution d’équilibrage de charge logicielle prise en charge. Étant donné que nous divisons le trafic de cette façon, nous devons remplacer le nom de domaine complet du pool de services web interne. Sinon, si nous avions un équilibreur de charge de ligne supérieure et envoyé tout le trafic via celui-ci au lieu d’utiliser l’équilibrage de charge DNS pour le trafic SIP, nous n’aurions pas besoin de remplacer l’URL des services web. 
    
    Dans la section DNS de cette rubrique, nous avons créé un enregistrement A pour `webint.contoso.local`. Il s’agit de l’URL que nous utilisons pour le trafic HTTP/S des services web, et elle doit passer par l’équilibreur de charge logiciel pris en charge que nous avons configuré. Par conséquent, dans cet exemple, nous substituons l’URL pour informer Skype Entreprise Server que tout le trafic HTTP/S doit aller à `webint.contoso.local` la place, `pool.contoso.local`comme illustré dans la figure. Pour plus d’informations sur l’équilibrage de charge, consultez [les exigences d’équilibrage de charge pour Skype Entreprise](../../plan-your-deployment/network-requirements/load-balancing.md).
    
    > [!IMPORTANT]
    > L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services web du pool est `https://webint.contoso.local`, l’URL de base est `webint.contoso.local`. 
  
    - Si vous configurez l’équilibrage de charge DNS, comme nous le faisons dans cet exemple, activez la case à cocher Remplacer le nom de domaine complet du **pool de services Web internes** , puis entrez l’URL de base interne (qui doit être différente du nom de domaine complet du pool) dans l’URL **de base interne**. 
    
    > [!CAUTION]
    > Si vous décidez de remplacer les services web internes par un nom de domaine complet autodéfini, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool d’administrateurs. **Utilisez uniquement des caractères standard** (y compris A-Z, a-z, 0-9 et traits d’union) lorsque vous définissez des URL ou des noms de domaine complets. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans une URL ou un nom de domaine complet ne sont souvent pas pris en charge par les autorités de certification externes et publiques (CA) (c’est-à-dire lorsque l’URL ou le nom de domaine complet doit être affecté au nom de l’objet ou à l’autre nom de l’objet dans le certificat).
  
    - Si vous le souhaitez, entrez l’URL de base externe dans **l’URL de base externe**. Vous devez entrer l’URL de base externe pour la différencier de votre nom de domaine interne. Par exemple, votre domaine interne est `contoso.local`, mais votre nom de domaine externe est `contoso.com`. Vous devez définir l’URL à l’aide du `contoso.com` nom de domaine, car elle doit être résolvable à partir du DNS public. Ceci est également important dans le cas d’un proxy inverse. Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse. L’accès HTTP au pool frontal est requis pour la messagerie instantanée et la présence sur les clients mobiles.
    
      ![Remplacez les services web.](../../media/8f95313c-2df4-4885-adc5-9fc9ea775406.png)
  
11. Si vous avez sélectionné **Conférence** dans la page **Sélectionner des fonctionnalités**, vous êtes invité à sélectionner un serveur Office Web Apps. Cliquez sur **Nouveau** pour lancer la boîte de dialogue.
    
12. Dans la boîte de **dialogue Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre serveur Office Web Apps dans la zone **de nom** de domaine complet du serveur Office Web Apps ; lorsque vous effectuez cette opération, votre Office Web Apps  L’URL de découverte du serveur doit être automatiquement entrée dans la **zone d’URL de découverte du serveur Office Web Apps**.
    
    Si le serveur Office Web Apps est installé localement et dans la même zone réseau que Skype Entreprise Server, ne sélectionnez pas l’option **Office Web Apps serveur est déployé dans un réseau externe (c’est-à-dire, périmètre/Internet).**
    
    Si le serveur Office Web Apps est déployé en dehors de votre pare-feu interne, sélectionnez l’option **Office Web Apps Serveur est déployé dans un réseau externe (c’est-à-dire, périmètre/Internet).**
    
13. Cliquez sur **Terminer** pour terminer la configuration. Si vous avez défini d’autres serveurs de rôles sur les **rôles de serveur associés à cette page de pool frontal** , des pages distinctes de l’Assistant Configuration de rôle s’ouvrent, où vous pouvez configurer les rôles serveur. Dans cet exemple, nous avons choisi uniquement la conférence.
    
### <a name="configure-simple-urls"></a>Configurer des URL simples

1. Dans le Générateur de topologie, cliquez avec le bouton droit sur le **Skype Entreprise Server** nœud supérieur, puis cliquez sur **Modifier les propriétés**, comme illustré dans la figure.
    
     ![Cliquez avec le bouton droit sur Skype Entreprise Server et sélectionnez Modifier les propriétés.](../../media/692c18dd-8e99-4239-ae7b-5e855d866afa.png)
  
2. Dans le volet **URL simples**, sélectionnez **Téléphone URL d’accès :** (connexion) ou **URL de réunion :** (Réunion) à modifier, puis cliquez sur **Modifier l’URL**.
    
3. Mettez à jour l’URL avec la valeur voulue, puis cliquez sur **OK** pour l’enregistrer. Vous devez configurer l’URL simple à l’aide du domaine SIP externe afin que les utilisateurs externes puissent participer à des réunions, par exemple, `contoso.com`qui sont externes, par opposition à `contoso.local`un domaine interne. Par conséquent, le domaine SIP doit être en mesure d’être résolu par un DNS externe.
    
4. Modifiez l’URL Meet en procédant de la même manière, si nécessaire.
    
### <a name="to-define-the-optional-admin-simple-url"></a>Pour définir l’URL simple Admin facultative

1. Dans le Générateur de topologie, cliquez avec le bouton droit sur le **nœud Skype Entreprise Server**, puis cliquez sur **Modifier les propriétés**.
    
2. Dans la zone **URL d’accès administratif**, entrez l’URL simple souhaitée pour l’accès administratif à Skype Entreprise Server Panneau de configuration, puis cliquez sur **OK**.
    
    > [!TIP]
    > Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL Admin. L’option la plus simple est https://admin. _\<domain\>_. L’URL Administration peut être un domaine interne ou externe, par exemple, `contoso.local` ou, tant que l’un ou `contoso.com`l’autre enregistrement peut être résolu dans le DNS interne. 
  
    > [!IMPORTANT]
    > Si vous modifiez une URL simple après le déploiement initial, vous devez être conscient des modifications qui affectent vos enregistrements et certificats DNS (Domain Name System) pour les URL simples. Si la modification affecte la base d’une URL simple, vous devez également modifier les enregistrements et certificats DNS. Par exemple, la modification de l’URL de base à partir de `https://sfb.contoso.com/Meet` `https://meet.contoso.com` sfb est modifiée.`contoso.com` vers `meet.contoso.com`, vous devez donc modifier les enregistrements et certificats DNS à faire `meet.contoso.com`référence à . Si vous avez remplacé l’URL simple par l’URL de `https://sfb.contoso.com/Meet` `https://sfb.contoso.com/Meetings`base, l’URL de `sfb.contoso.com` base reste la même, donc aucune modification du DNS ou du certificat n’est nécessaire. Toutefois, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter l’applet de commande **Enable-CsComputer** sur chaque serveur d’annuaire et de serveur frontal pour inscrire la modification.
  
### <a name="publish-and-verify-the-topology"></a>Publier et vérifier la topologie

1. Vérifiez que toutes les URL simples sont configurées correctement.
    
2. Vérifiez que le serveur basé sur SQL Server est en ligne et disponible sur l’ordinateur sur lequel le Générateur de topologie est installé, y compris les règles de pare-feu nécessaires.
    
3. Vérifiez que le partage de fichiers est disponible et que les autorisations appropriées sont définies.
    
4. Confirmez que les rôles serveur corrects qui répondent à la configuration requise pour le déploiement sont définis dans la topologie.
    
5. Vérifiez que les serveurs existent dans services de domaine Active Directory (AD DS). Cela se produit automatiquement lorsque vous joignez les serveurs au domaine.
    
    Lorsque vous avez vérifié la topologie et qu’aucune erreur de validation n’a été détectée, vous êtes prêt à publier la topologie. En cas d’erreurs de validation, vous devez les corriger avant de pouvoir publier la topologie.
    
6. Cliquez avec le bouton droit sur le **nœud Skype Entreprise Server**, puis cliquez sur **Publier la topologie**.
    
7. Dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
8. Dans la page **Sélectionner un serveur d’administration centrale** , sélectionnez un pool frontal, comme illustré dans la figure.
    
    > [!NOTE]
    > Vous pouvez cliquer sur **Avancé** pour configurer les emplacements des fichiers de base de données.
  
     ![Sélectionnez serveur du Magasin de gestion centrale.](../../media/764478b5-8480-42c5-854f-649bb121cd94.png)
  
9. Dans la page **Sélectionner des bases de données** , sélectionnez les bases de données que vous souhaitez publier.
    
    > [!NOTE]
    > Si vous n’avez pas les droits appropriés pour créer les bases de données, vous pouvez décocher les cases en regard de ces bases de données, et une personne disposant des droits appropriés peut créer ultérieurement les bases de données. Pour plus d’informations sur les exigences, consultez [La configuration requise du serveur pour Skype Entreprise Server](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
10. Vous pouvez cliquer sur **Avancé**. À l’aide des options de placement de fichiers de données Advanced SQL Server, vous pouvez choisir entre les options suivantes : 
    
    - **Déterminer automatiquement l’emplacement du fichier de base de données** : cette option détermine les meilleures performances opérationnelles en fonction de la configuration du disque sur votre serveur basé sur SQL Server en distribuant les fichiers journaux et de données au meilleur emplacement.
    
    - **Utilisez SQL Server instance par défaut** : cette option place les fichiers journaux et de données sur le serveur basé sur SQL Server à l’aide des paramètres d’instance. Elle ne fait pas appel à la fonctionnalité d’analyse opérationnelle de SQL Server qui permet de déterminer le meilleur emplacement des fichiers journaux et de données. L’administrateur SQL Server place généralement les fichiers journaux et de données à des emplacements conformes aux procédures de gestion des serveurs SQL Server et de l’organisation.
    
    Cliquez sur **OK**, puis sur **Suivant**. 
    
11. Si vous le souhaitez, cliquez sur **Avancé**. À l’aide des options de placement de fichiers de données Advanced SQL Server, vous pouvez choisir entre les options suivantes : 
    
    - **Déterminer automatiquement l’emplacement du fichier de base de données** : cette option détermine les meilleures performances opérationnelles en fonction de la configuration du disque sur votre serveur basé sur SQL Server en distribuant les fichiers journaux et de données au meilleur emplacement.
    
    - **Utilisez SQL Server instance par défaut** : cette option place les fichiers journaux et de données sur le serveur basé sur SQL Server à l’aide des paramètres d’instance. Elle ne fait pas appel à la fonctionnalité d’analyse opérationnelle de SQL Server qui permet de déterminer le meilleur emplacement des fichiers journaux et de données. L’administrateur SQL Server place généralement les fichiers journaux et de données à des emplacements conformes aux procédures de gestion des serveurs SQL Server et de l’organisation.
    
    Cliquez sur **OK**.
    
12. Cliquez sur **Suivant** pour terminer le processus de publication.
    
    > [!NOTE]
    > Un échec courant de cette étape est que les bases de données SQL Server ne peuvent pas être créées. Lorsque le processus ne peut pas se terminer, une erreur est fournie, comme illustré dans la figure. La cause la plus probable est que l’utilisateur qui tente de créer la base de données ne dispose pas des autorisations appropriées, ou que le système SQL Server ne peut pas être contacté en raison d’un pare-feu ou d’un autre problème réseau. 
  
     ![Erreur lors de la création d’un magasin de gestion centralisée.](../../media/558bd2e4-2721-422d-9986-df86f642e6a1.png)
  
13. Une fois le processus de publication terminé, un lien s’affiche pour ouvrir une liste des étapes suivantes. Cliquez **ici pour ouvrir la liste des tâches** pour afficher les étapes suivantes, puis cliquez sur **Terminer**. 
    
    Le message « Terminé avec avertissements » pour la création de la base de données ne signifie pas qu’il y a eu une erreur. Le processus d’installation doit modifier les paramètres dans SQL Server pour que Skype Entreprise Server fonctionne correctement. Lorsqu’un paramètre est modifié dans SQL Server, il est enregistré en tant qu’avertissement afin que SQL Server administrateurs puissent comprendre exactement ce que le processus d’installation a terminé. Si vous recevez un avertissement, vous pouvez sélectionner l’enregistrement, puis cliquer sur **Afficher les journaux** pour afficher les détails de l’avertissement.
    
    Une fois la topologie publiée, vous pouvez commencer à installer un réplica local du magasin de gestion centrale sur chaque serveur exécutant Skype Entreprise Server dans votre topologie. Nous vous recommandons de commencer par le premier pool frontal. 
