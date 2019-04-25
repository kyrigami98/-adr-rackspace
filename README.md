# -adr-rackspace
Projet d'architecture des logiciels

Établir un ADR aposteriori comprenant les 3 entrées correspondant aux 3 versions majeures. Chaque entrée comportera :
• un contexte, la problématiques, les cas d’utilisation 
• les scénarios d’attribut de qualité mis en avant
• des vues de structures architecturales pertinentes au regard des attributs choisis


Developpement de l'ADR: Kyriel DOSSOU
---------------------------------------------------------------------------------------------------------------------------------
Version 1
---------------------------------------------------------------------------------------------------------------------------------
=>Contexte:  
Les Logs étaient stockés dans des fichiers de texte plats sur le disque local de chaque serveur de messagerie et étaient conservés pendant 14 jours. Les techniciens de support n’étaient pas connectés aux serveurs. Par conséquent, pour pouvoir rechercher les logs, ils devaient transmettre un ticket aux ingénieurs qui devais se connecter par ssh et chercher les fichiers. 

=>Problématiques:
Le processus manuel de connexion à chaque serveur prend trop de temps aux ingénieurs une fois dépassé la douzaine de serveurs.

=>les cas d’utilisation:
  - Envoyer les tickets
  - Se connecter au server
  - Chercher les fichiers de logs
  
=> les scénarios d’attribut de qualité mis en avant:

-Attribut de qualité: Performance, Testabilité
-Source: Envoi de tichet par un technicien
-Stimulus: erreur de transmission de ticket
-Artefact: serveurs de logs
-Environnement: verifications de la validations des tickets
-Réponse:
  • Enregistrer la défaillance
  • Aviser les techniciens et les ingénieurs de la cause de l'erreur de transmission de ticket

-Mesure de réponse:
  • Sensibilisé les techniciens sur la validité des tickets à envoyer au ingénieurs
  • Contacter le techniciens responsable de l'envoi du ticket pour verification d'identité

=> des vues de structures architecturales pertinentes au regard des attributs choisis:



Version 2
------------------------------------------------------------------------------------------------------------------------------------
=>Contexte:  
Un outil Web de recherche de journal permet aux techniciens du support technique de rechercher les journaux, sans impliquer les ingénieurs.Il permettait de rechercher l'adresse de messagerie, le nom de domaine ou l'adresse IP de l'expéditeur ou du destinataire Les journaux de chaque jour étaient stockés dans une table séparée, afin de pouvoir nettoyer les anciennes données en supprimant et en recréant simplement les tables MySQL.Les données de journal  étaient conservées que pendant 3 jours afin de maintenir la base de données MySQL à une taille raisonnable.

=>Problématiques:
- Au fur et à mesure que les tables grandissaient, l'indexation de chaque entrée insérée devenait lente. 
- Lorsque nous atteignions environ 100 serveurs, les opérations de chargement de la base de données prenaient plus de temps.

=>les cas d’utilisation:
 
 - Rechercher un clients
 - Supprimer les tables sql
 - Supprimer les données de log
 - Visualiser le chargement de la base de donnée

=> les scénarios d’attribut de qualité mis en avant:

- Attribut de qualité: La performance, disponibilité
- Source: Rechercher un client
- Stimulus: Client introuvable
- Artefact: Base de donnée MySql
- Environnement: gestion et tri des fichiers de log via une Base de donnée
- Réponse: 
  • Enregistrer la défaillance
  • Aviser les techniciens et les ingénieurs de la cause de l'erreur de transmission de ticket
- Mesure de réponse:
  • Enregistrer la défaillance
  • Aviser les techniciens et les ingénieurs de la cause de l'erreur de transmission de ticket
  
=> des vues de structures architecturales pertinentes au regard des attributs choisis:

Version 3
------------------------------------------------------------------------------------------------------------------------------------

=>Contexte:  

=>Problématiques:

=>les cas d’utilisation:

=> les scénarios d’attribut de qualité mis en avant:

Attribut de qualité:
Source:
Stimulus:
Artefact:
Environnement:
Réponse:
Mesure de réponse:

=> des vues de structures architecturales pertinentes au regard des attributs choisis:
