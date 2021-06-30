task :parse_data_file do
  require 'yaml'
  infractions_file = File.join(__dir__, 'infractions.yml')
  YAML.parse(File.read(infractions_file))
end

# Ensures that each item in infractions.yml has at least one term and alternative.
task :validate_data do
  require 'yaml'
  infractions_file = File.join(__dir__, 'infractions.yml')
  infractions = YAML.load(File.read(infractions_file))
  error_message = ''
  if infractions.any? { |i| i['terms'].nil? || i['terms'].empty? }
    error_message += 'Each infraction must contain at least one term.'
  end
  if infractions.any? { |i| i['alternatives'].nil? || i['alternatives'].empty? }
    error_message += 'Each infraction must contain at least one alternative.'
  end
  raise error_message unless error_message.empty?
end

# Ensures that the script to generate a woke config file produces valid YAML.
task :validate_woke_adapter do
  require 'yaml'
  infractions_file = File.join(__dir__, 'infractions.yml')
  generate_script = File.join(__dir__, 'generate_woke_config')
  output = `#{generate_script} #{infractions_file}`
  woke_config = YAML.load(output)
  if woke_config['rules'].nil? || woke_config['rules'].empty?
    raise 'Woke config contains no entries'
  end
end
