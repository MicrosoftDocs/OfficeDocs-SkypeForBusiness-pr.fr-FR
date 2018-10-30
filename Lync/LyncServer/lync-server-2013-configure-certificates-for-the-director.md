---
title: 'Lync Server 2013 : Configuration des certificats pour le directeur'
TOCTitle: Configuration des certificats pour le directeurr
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398296(v=OCS.15)
ms:contentKeyID: 49296495
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des certificats pour le directeur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

> [!IMPORTANT]  
> Lorsque vous exécutez l’Assistant Certificat, assurez-vous d’être connecté à l’aide d’un compte membre d’un groupe auquel ont été affectées les autorisations appropriées pour le type de modèle de certificat que vous utiliserez. Par défaut, une demande de certificat Lync Server 2013 utilise le modèle de certificat Serveur web. Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat utilisant ce modèle, vérifiez que les autorisations Inscrire requises pour utiliser ce modèle ont été affectées au groupe.

Chaque directeur requiert un certificat par défaut, un certificat web interne et un certificat web externe. Pour plus d’informations sur les exigences en matière de certificat des directeurs, reportez-vous à [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.

Configurez les certificats de directeur en suivant la procédure ci-dessous. Répétez la procédure pour chaque directeur. Les étapes de cette procédure expliquent comment configurer un certificat à partir d’une autorité interne de certification racine d’entreprise déployée par votre organisation et avec le traitement des requêtes hors connexion. Pour plus d’informations sur l’obtention de certificats issus d’une autorité de certification externe, contactez votre équipe de support.

## Pour configurer les certificats du directeur ou du pool directeur

1.  Dans l’Assistant Déploiement de Lync Server, en regard de l’**Étape 3 : Demander, installer ou affecter les certificats** , cliquez sur **Exécuter** .

2.  Dans la page **Assistant Certificat** , cliquez sur **Demander** .

3.  Dans la page **Demande de certificat** , cliquez sur **Suivant** .

4.  Dans la page **Demandes différées ou immédiates** , acceptez l’option par défaut, **Envoyer la demande immédiatement à une autorité de certification en ligne** , puis cliquez sur **Suivant** .

5.  Dans la page **Choisir une autorité de certification** , cliquez sur l’autorité de certification Windows interne voulue, puis cliquez sur **Suivant** .

6.  Dans la page **Compte d’autorité de certification** , indiquez d’autres informations d’identification à utiliser au cas où le compte auquel vous êtes connecté ne dispose pas de l’autorité nécessaire pour demander le certificat, puis cliquez sur **Suivant** .

7.  Dans la page **Spécifier un autre modèle de certificat** , cliquez sur **Suivant** .

8.  Dans la page **Nom et paramètres de sécurité** , vous pouvez indiquer un **nom convivial** et accepter la longueur de clé de 2048 bits, puis cliquez sur **Suivant** .

9.  Dans la page **Informations relatives à l’organisation** , indiquez, si vous le souhaitez, des informations sur l’organisation, puis cliquez sur **Suivant** .

10. Dans la page **Informations géographiques** , indiquez, si vous le souhaitez, des informations géographiques, puis cliquez sur **Suivant** .

11. Dans la page **Nom de sujet / Autres noms de sujet** , cliquez sur **Suivant** .
    
    > [!NOTE]  
    > La liste des autres noms de sujet devrait contenir le nom de l’ordinateur sur lequel vous installez le directeur (s’il n’y en a qu’un) ou le nom du pool directeur ainsi que le nom des URL simples configurés pour l’organisation.

12. Dans la page **Paramètre du domaine SIP sur les autres noms du sujet** , sélectionnez **Domaines SIP configurés** pour tous les domaines devant être gérés par le directeur, puis cliquez sur **Suivant** .

13. Dans la page **Configurer d’autres noms du sujet supplémentaires** , ajoutez des noms de sujet supplémentaires, puis cliquez sur **Suivant** .

14. Dans la page **Résumé de la demande de certificat** , cliquez sur **Suivant** .

15. Dans la page **Exécution de commandes** , cliquez sur **Suivant** une fois les commandes exécutées.

16. Dans la page **État de la demande de certificat en ligne** , cliquez sur **Suivant** .

17. Dans la page **Affectation de certificat** , cliquez sur **Suivant** .
    
    > [!NOTE]  
    > Si vous souhaitez afficher le certificat, double-cliquez sur celui-ci dans la liste.

18. Dans la page **Résumé de l’affectation du certificat** , cliquez sur **Suivant** .

19. Dans la page **Exécution de commandes** , cliquez sur **Terminer** une fois les commandes exécutées.

20. Dans la page **Assistant Certificat** , cliquez sur **Fermer** .

