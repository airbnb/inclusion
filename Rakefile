task :parse_data_file do
  require 'yaml'
  infractions_file = File.join(__dir__, 'infractions.yml')
  YAML.parse(File.read(infractions_file))
end
